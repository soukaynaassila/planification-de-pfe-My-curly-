My Curly – Functional Specifications Document
1. Project Overview
Project Name

My Curly

Project Description

My Curly is a web platform dedicated to people with curly hair. The application combines an e-commerce store, a blog, and an appointment booking system. Users can purchase curly hair products, read educational articles, and book salon services online.

Objectives
Sell curly hair products online.
Provide educational content through blog articles.
Allow users to book salon appointments.
Offer a complete user experience through account management, orders, and reservations.

2. Functional Requirements
Visitor Features ==
View products.
Search products.
Read blog articles.
View services.
Register an account.
Login.

User Features ==
Manage profile.
Add products to cart.
Update cart quantities.
Place orders.
View order history.
Add comments on blog posts.
Like blog articles.
Book appointments.

Administrator Features ==
Dashboard with statistics.
Manage products.
Manage orders.
Manage reservations.
Manage blog articles.
Approve or reject comments.

 
3. Project Structure (My Curly)

My-curly2/
│
├── index.php
│
├── admin/
│   ├── dashboard.php
│   ├── products.php
│   ├── add-product.php
│   ├── edit-product.php
│   ├── orders.php
│   ├── reservations.php
│   ├── comments.php
│   ├── blog.php
│   └── users.php
│
├── auth/
│   ├── login.php
│   ├── register.php
│   └── logout.php
│
├── user/
│   ├── index.php
│   ├── products.php
│   ├── product.php
│   ├── cart.php
│   ├── checkout.php
│   ├── orders.php
│   ├── blog.php
│   ├── article.php
│   ├── reservation.php
│   └── profile.php
│
├── api/
│   ├── cart/
│   ├── blog/
│   ├── comments/
│   ├── likes/
│   ├── orders/
│   ├── products/
│   └── reservations/
│
├── includes/
│   ├── header.php
│   ├── footer.php
│   ├── admin-header.php
│   ├── admin-footer.php
│   ├── auth.php
│   ├── response.php
│   ├── sanitize.php
│   ├── upload.php
│   └── validate.php
│
├── middleware/
│   ├── auth.php
│   ├── admin.php
│   ├── api.php
│   └── api_admin.php
│
├── config/
│   ├── database.php
│   ├── bootstrap.php
│   └── session.php
│
├── uploads/
│   ├── products/
│   └── blog/
│
├── css/
│   └── main.css
│
├── js/
│   └── app.js
│
└── database/
    ├── mycurly.sql
    ├── migration_v2.sql
    ├── migration_v2_rollback.sql
    └── images/


Folder Description

* **admin/** : Administration dashboard and management pages.
* **auth/** : User authentication (login, register, logout).
* **user/** : Public website pages accessible to users.
* **api/** : AJAX endpoints used by JavaScript and frontend features.
* **includes/** : Reusable components and helper files.
* **middleware/** : Authentication and authorization controls.
* **config/** : Application configuration and database connection.
* **uploads/** : Uploaded images for products and blog posts.
* **css/** : Stylesheets.
* **js/** : JavaScript files.
* **database/** : SQL schema, migrations, and database resources.
* **index.php** : Redirects visitors to the application's homepage.

````

**Root Redirect**

```php
<?php
header('Location: /My-curly2/user/index.php');
exit;
````

4. Database Schema

Users

Field	Type

id	    INT
name	VARCHAR
email	VARCHAR
avatar 	varchar	
password	VARCHAR
role	   ENUM
is_active   tinyint
created_at	TIMESTAMP
updated_at  TIMESTAMP

************************
Categories

Field	 Type

id	     INT
name	VARCHAR
slug 	varchar
description	 text
image   VARCHAR
sort_order   INT
is_active   tinyint
created_at   TIMESTAMP
updated_at   TIMESTAMP
************************
Products

Field	Type

id	     INT
category_id  int
name	VARCHAR
slug 	varchar
sku    VARCHAR
description	TEXT
price	DECIMAL
stock	INT
is_active 	tinyint
created_at	timestamp
updated_at	timestamp

************************
Product_images

Field	Type

id	     INT
product_id 	int
image	varchar
alt_text	varchar
sort_order	int
is_primary	tinyint
created_at	timestamp
**************************

Blog Posts

Field	Type

id	INT
title	VARCHAR
slug	VARCHAR
excerpt	TEXT
content	LONGTEXT
image	VARCHAR
author	varchar
author_id 	int
views	int
is_published tinyint
created_at	timestamp
updated_at	timestamp
**************************
Comments

Field	Type

id	INT
parent_id	int
post_id	 varchar
user_id	 INT
username varchar
is_approved	tinyint
created_at	timestamp
updated_at	timestamp
**************************
likes

Field	Type

id	INT
post_id	 varchar
user_id	 INT
session_id 	varchar
created_at	timestamp
**************************
Orders

Field	Type

id	INT
user_id	INT
total	DECIMAL
status	ENUM
shipping_name	VARCHAR
shipping_address	VARCHAR
shipping_city	VARCHAR
shipping_zip  VARCHAR
shipping_country  VARCHAR
shipping_phone	VARCHAR
notes	text
payment_method	varchar
payment_status 	enum
transaction_id	varchar
created_at	timestamp
updated_at	timestamp
**************************
Order Items

Field	Type

id	INT
order_id	INT
product_id	INT
product_name	VARCHAR
price	decimal
quantity	INT
discount_amount	 decimal
subtotal	decimal
**************************
Cart Items

Field	Type

id	INT
user_id	INT
product_id	INT
quantity	INT
created_at	timestamp	
updated_at	timestamp	
**************************
Reservations

Field	Type

id	INT
user_id	INT
name	VARCHAR
email	VARCHAR
phone	VARCHAR
service	VARCHAR
service_id	int
date	DATE
time	TIME
time_new	time
notes	text
status	ENUM
created_at	timestamp
updated_at	timestamp
**************************
services

Field	Type
id 	    int
name	varchar
slug 	varchar
description	text
duration	smallint
price	decimal
is_active	tinyint
sort_order	int
created_at	timestamp
**************************
MCD(Relationships) 
USER
  |
  | (1,N)
  |
PLACES
  |
  | (1,1)
  |
ORDER

USER
  |
  | (1,N)
  |
WRITES
  |
  | (1,1)
  |
COMMENT
  |
  | (N,1)
  |
BLOG_POST

USER
  |
  | (1,N)
  |
LIKES
  |
  | (N,1)
  |
BLOG_POST

CATEGORY
  |
  | (1,N)
  |
PRODUCT

USER
  |
  | (1,N)
  |
CART_ITEM
  |
  | (N,1)
  |
PRODUCT

ORDER
  |
  | (1,N)
  |
ORDER_ITEM
  |
  | (N,1)
  |
PRODUCT

USER
  |
  | (0,N)
  |
RESERVATION

6. Technologies Used
PHP 8
MySQL
PDO
HTML5
CSS3
JavaScript
AJAX
XAMPP
7. Conclusion

My Curly is a complete web application that combines online shopping, educational content, and salon appointment management. The platform is designed to improve the experience of people with curly hair by providing products, information, and services in a single ecosystem