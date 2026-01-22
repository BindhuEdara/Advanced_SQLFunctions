## Database Relationships ?

   A Database Relationship defines how two or more tables are connected to each other using keys(primary Key and Foreign Key).
   It helps organize data, reduce duplication, and maintain data consistency.

## Types of Data Relationships?

 There are three main types of database relationships:
   ## 1. One-to-One
   ## 2. One-to-Many
   ## 3. Many-to-Many

## 1. One-to-One Relationship:-
    In a one-to-one Relationship, one record in Table A is linked to only one record in Table B, and viceversa.
   __Ex:__ In E-commerce user has only one profile and that profile belongs to only one user.
   __Ex:__ users and userProfiles are the tables

   _users_
   -------
    user_id(primary key)
    name
    email

             1------------1

   _userProfiles_
   ---------------
   profile_id(primary key)
   user_id(foreign key)
   address
   phone

   user_id in userProfiles is a **foreign key**, Ensures each user has only one profile.

  ## 2. One-to-Many Relationship:-

    In a one-to-many relationship, one record in Table A can be linked to multiple records in Table B, but each record in Table B is linked to only one record in Table A.

     __Ex:__ In E-commerce one customer can place many orders, each order belongs to one customer.

     __Ex:__ Customers and Orders are the Tables.

     _Customers_
     -------------
     customer_id(primary key)
     name
     email

               1 ------------ Infinity

     _Orders_
     -----------
     order_id(primary key)
     customer_id(foreign Key)
     order_date
     total_amount

     customer_id in orders connects orders to customers, most common relationship in databases.

  ## 3. Many-to-Many Relationship:-

     In a many-to-many relationship, multiple records in Table A relate to multiple records in Table B.
     This relationship requires a junction (bridge) table.

     __Ex:__  In E-commerce one order can contain many products and one product can appear in many orders.

     __Ex:__ Orders , Products and OrderItems(Junction table)

     _orders_                  _orderItems_                     _products_
     ----------               ---------------                  --------------
     order_id(primary key)   1 ----order_id(FK)----Infinity     product_id(PK)
                                product_id(FK)
                                quantity
                                price
    orderItems connects orders and products , It stores extra details like quantity and price.
