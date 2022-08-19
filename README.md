# 13 Object Relational Mapping (ORM): E-commerce Back End

This project was to build the API routes and models for Sequelize to create the back-end database for an E-Commerce style business, in this case a general store. The API routes created were to be used for back-end CRUD (Create, Read, Update, Delete) functions for our database. These routes will use the Sequelize models created and Sequelize methods to perform these actions on our data.

Much of the code in this project was supplied and can be seen here: [starter code](https://github.com/coding-boot-camp/fantastic-umbrella)

Video demonstration can be found here: [E-Commerce Back End Demo](https://www.youtube.com/watch?v=zhKH6oT9lG0)


## User Story

```md
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

## Acceptance Criteria

```md
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database
```


## Primary Tools

This application primarily uses these Node packages:

* [MySQL2](https://www.npmjs.com/package/mysql2) 
* [Sequelize](https://www.npmjs.com/package/sequelize) 
* [dotenv package](https://www.npmjs.com/package/dotenv) 

## Starting the Application

To start the application, you must install the node modules and packages necessary which can be done using this command in the terminal at the root of the project:

```
npm i
```

 You must then create a .env file at the root of the project with the db name, db user and db password in the following format:

```
DB_NAME=ecommerce_db
DB_USER=
DB_PW=
```

Create the database by running mysql in the terminal and using:

```
source db/schema.sql
```

After creating the database, you can exit mysql and in the terminal can then create the seed data using this command:

```
npm run seed
```

Finally, you can then start the application and server using the command:

```
npm start
```


### Database Models

The database tables created using Sequelize models:

* `Category`

  * `id`
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment

  * `category_name`
    * String
    * Doesn't allow null values

* `Product`

  * `id`
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment

  * `product_name`
    * String
    * Doesn't allow null values

  * `price`
    * Decimal
    * Doesn't allow null values
    * Validates that the value is a decimal

  * `stock`
    * Integer
    * Doesn't allow null values
    * Set a default value of 10
    * Validates that the value is numeric

  * `category_id`
    * Integer
    * References the `category` model's `id` 

* `Tag`

  * `id`
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment

  * `tag_name`
    * String

* `ProductTag`

  * `id`
    * Integer
    * Doesn't allow null values
    * Set as primary key
    * Uses auto increment

  * `product_id`
    * Integer
    * References the `product` model's `id`

  * `tag_id`
    * Integer
    * References the `tag` model's `id`



## Product

Video demonstration can be found here: [E-Commerce Back End Demo](https://www.youtube.com/watch?v=zhKH6oT9lG0)

Below are several gifs demonstrating the application as well.

### DB Schema, Seeds and Starting Server Demo

![Demo gif for initial setup of the project](./assets/init-demo.gif)

### Categories Demo

![Demo gif for the category routes](./assets/categories-demo.gif)

### Tags Demo

![Demo gif for the tag routes](./assets/tags-demo.gif)

### Products Demo

![Demo gif for the product routes](./assets/products-demo.gif)