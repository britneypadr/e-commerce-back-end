# E-commerce Back End

## Description
This project is a back-end application for an e-commerce site built using Express.js, Sequelize, and MySQL. It provides RESTful APIs for managing categories, products, and tags. The application uses Sequelize ORM to interact with a MySQL database and dotenv to manage environment variables securely.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Database Models](#database-models)
- [API Routes](#api-routes)
- [Associations](#associations)
- [Walkthrough Video](#walkthrough-video)
- [License](#license)

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/britneypadr/e-commerce-back-end
   cd your-repo

2. Install the necessary dependencies:
```sh
npm install

4. Create a '.env' file in the root directory with the following content:
```sh
DB_NAME='your_database_name'
DB_USER='your_mysql_username'
DB_PASSWORD='your_mysql_password'

5. Create the database using the schema provided in the 'db' folder:
```sh
mysql -u your_mysql_username -p < db/schema.sql

6. Seed the database:
```sh
npm run seed

## Usage
1. Start the server:
```sh
npm start

2. The server will start on http://localhost:3000. Use an API client like Insomnia  to test the API routes.

## Database Models

The database contains the following models:

Category
```sh
id (Integer, Primary Key, Auto Increment, Not Null)
category_name (String, Not Null)

Product
```sh
id (Integer, Primary Key, Auto Increment, Not Null)
product_name (String, Not Null)
price (Decimal, Not Null)
stock (Integer, Not Null, Default Value: 10)
category_id (Integer, References Category.id)

Tag
```sh
id (Integer, Primary Key, Auto Increment, Not Null)
tag_name (String)

ProductTag
```sh
id (Integer, Primary Key, Auto Increment, Not Null)
product_id (Integer, References Product.id)
tag_id (Integer, References Tag.id)

API Routes
The application provides the following API routes for managing categories, products, and tags:

Categories
```sh
GET /api/categories - Get all categories
GET /api/categories/:id - Get a category by ID
POST /api/categories - Create a new category
PUT /api/categories/:id - Update a category by ID
DELETE /api/categories/:id - Delete a category by ID

Products
```sh
GET /api/products - Get all products
GET /api/products/:id - Get a product by ID
POST /api/products - Create a new product
PUT /api/products/:id - Update a product by ID
DELETE /api/products/:id - Delete a product by ID

Tags
```sh
GET /api/tags - Get all tags
GET /api/tags/:id - Get a tag by ID
POST /api/tags - Create a new tag
PUT /api/tags/:id - Update a tag by ID
DELETE /api/tags/:id - Delete a tag by ID

Associations
The following associations are established between the models:

Product belongs to Category
Category has many Product
Product belongs to many Tag through ProductTag
Tag belongs to many Product through ProductTag

## Walkthrough Video

A walkthrough video demonstrating the functionality of the application can be found here.

## License
This project is licensed under the MIT License.
