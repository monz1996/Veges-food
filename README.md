# Veges-food
Problem
Create an E-commerce website which had Users and Admins Using Java Core and Java EE.
It needed to include many functionalities such as:
- User : Login and logout of the system, Cart, Order, Search Products and Update Profile.
- Admin: View all User’s profiles and Order history and Update the products.

IDEA
1- MODEL: Model class for each Entity (User, Admin, Product, Cart... etc.)
2- Controller: A Servlet that takes the requests and calls the required service class and hanldes
exceptions.
3- Service: Calls the DAOs for the required functionalities and throws Exceptions.
4- DAO: A class responsible for establishing connection with the DB using Hibernate and JSP to
perform basic CRUD operations.
5- MySql- Connect the project to MySQL to store all the data in.
6- UI- Create the UI of the website using JSPs, HTML, JS and Jquery.
7- CONNECTION- Finally connect between the back-end and the front-end.
What I did in this project was create all the models, routers and
fetchers.
Implementation
I created all the DAOS, Services and Controllers.
- Created all the custom exceptions required,
- In controllers, utilized Add,Get, Put, Post and Delete functionalities to reduce URLs and handle
requests, sent the response according to the data retrieved and exception handling.
- In the services called all the nessaccary DAOs to perform the Task and in the OrderService I
created a custom task that need to be done in the same Entity manager.
- In DAOs, Created a generic class which handles all the basic Crud operations and created a DAO
for each entity which extends the generic DAO minimizing the code
- In the CartItemDAO, I didn’t use an Entity Manager, instead I used the session to reduce DB load
and improve overall performance.

Result
The project worked very well and did what was needed, however there was an issue with the
session, it didn’t terminate when called the invalidate function because of the Server Container
(Tomcat)

Challenges

In a JSP while reading from the session we go Duplicate local variable user error, because there was
another JSP using using the same variable name and used the function include.

Issue with persisting the cartItem
because the User object and the Product object were not in the persistence context, When we tried
to get them from the merge function from their respected DAOs, it also failed, because they need to
be in the same entity manager persistence context
Different
- I would have improved the communication between me and the front end members, because it
created a lot of unnecessary issues
