Features Description:

The system developed will have the following features:-
1) Authentication:-

a) Signup : Any new user will fill up the form and a database entry will be made in   the user data base.

b) Login : If an existing user wants to order, he logs in using the email ID and password that will be matched with the database and then access will be given to the user to proceed further.

2) Order:-
a) View: The user can see the restaurants of his city, the menus of the corresponding restaurants with checkboxes and quantity and the estimated time for delivery. The estimated time will be calculated
b) Cart: The items selected will be shown in the cart. The user can add or delete the items, discard the entire order or checkout and proceed further.
c) Wishlist (additional feature): sometimes we crave for some food at an unusual hour. In the wishlist we can add those items and order them later.


3) Payment:-
a) Calculate Bill: The bill calculation will consider the following parameters:-
i) base bill= Σ item price*quantity
ii) the base bill must be above Rs.100 ie minimum order value.
iii) the delivery charges will be applied based on the distance between user and restaurant address.
iv) The user will have two promo codes:- SAVE50 and SAVE20 and each can	be used only once. 
b) Payment Mode:-
The payment can be done through online mode only for surety and safety purposes. It can be using UPI like google pay/bhim etc or netbanking or debit or credit card.




4) Tracking:- 
After the payment, the user can track the time. This module extracts the estimated time calculated and if the current time exceeds the estimated time by 10%, the user will have the option to cancel the order. 
If the user receives the order in time or does not cancel the order even after time exceeds and receives it, he can rate the app and food.


OO Design

Data Abstraction - Object oriented allows us to write the programs using classes and object. It is basically real world approach. The behavior and state of the objects of a class is same as the real world application. So we have created classes and objects for OO design. 
Inheritance- Inheritance is the property of the derived class to inherit the capabilities of it’s parent class.  We have inherited Calculate and Payment_method in Payment class and Order class inherits Cart class.
Encapsulation- It uses the idea of wrapping the state and behaviors that work on data within one unit. All the classes have its own state and behaviors defined in a unit called class.
Polymorphism -Polymorphism is the ability of data to be processed in more than one form. We have used functional overloading in Class Cart and Class Order. We have same methods viewResturants(self) in both classes. But the Order.viewResturant is overridden in Cart.viewResturant and estimatedTime() is used in this method.



SRP -  Single Responsibility Principle-  Every class has a responsibility of a single part of program's functionality, which is encapsulated.

Single responsibilities are like this :
CreateDataBase- creation of database and tables
CreateMenu- creation of restaurant, dishes and prices- in a menu pattern
Authentication- login and signup for users
Wishlist- creation of the wishlist of choice, view the restaurants, menu and add items to wishlist
Cart-  all cart operations- adding, delete, discard and confirm of the order will be done
Order- inherits Cart class, viewing the menu, restaurants, estimate the time of the user to the restaurant and start ordering.
Payment- it inherit Calculate and Payment_method class and starts the payment
Calculate- calculate the bill=- normal sum, checks minimum amount, coupons and gives final sum
Payment_method-different methods for payment eg. upi, debit/credit card and netbanking.
Timings- estimate the time required for an order to be delivered
Track-it tracks the delivery of order, ask for rating from user



OCP- Open-Closed Principle-  should be open for extension, but closed for modification

Open :  We can add new functionality without changing the existing code.  All the classes have one responsibility and are complete in themselves so if we want to add a feature, we can add it in a particular class as a functionality. This prevents situations in which a change in one also requires you to adapt all depending classes. So it is open to extension.
Closed : the classes Cart-->Order and Calculate,Payment_method-->Payment  follow inheritance. Cart is compiled and saved thus closed for modification but can be used inheritances, hence open to extension. It is extended using abstract method. 
Thus the project follows Open-Closed principle.


LSP Liskov Substitution Principle
LSP(The Liskov Substitution Principle) is defined as the object of the superclass can be replaced by the object of the subclass without any change in the application of the program. It is required for an object of the subclass to behave like the object of superclass. 
In the classes Cart-->Order follow inheritance where Cart is the super class and Order is the subclass. We have created object of Order class and it can act as a substitute of the parent class Cart. 
The method viewRestaurants() present in both the class. So the object of the subclass Order will replace the object of superclass Cart for this method.
Failing to follow LSP results in
OCP violations 
Strange code



