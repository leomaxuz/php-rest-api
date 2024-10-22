
# PHP REST API with MySQL

This project demonstrates how to create a basic REST API using PHP and MySQL. The API allows users to perform CRUD operations (Create, Read, Update, Delete) on product data, stored in a MySQL database.

## Features
- **Create**, **Read**, **Update**, and **Delete** (CRUD) operations.
- Well-structured and scalable PHP code.
- Uses PDO for secure database interaction.

## Technologies Used
- **PHP**: Backend logic for handling API requests and database operations.
- **MySQL**: Relational database to store product data.
- **PDO**: Secure connection to the MySQL database using PHP Data Objects.

## Project Structure
```
php-rest-api/
│
├── config/
│   └── Database.php       # Handles database connection
│
├── api/
│   └── Product.php        # Contains the API logic for retrieving products
│
├── models/
│   └── Product.php        # Product model with CRUD methods
│
├── index.php              # Entry point for the API
│
└── README.md              # Project description and setup guide
```

## Getting Started

### Prerequisites
- PHP >= 7.3
- MySQL
- Web server (e.g., Apache, Nginx)

### Setup Instructions
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/php-rest-api.git
   cd php-rest-api
   ```

2. **Import the database**:
   Import the `products` table using the SQL below:
   ```sql
   CREATE DATABASE api_db;
   USE api_db;
   CREATE TABLE products (
       id INT(11) AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       description TEXT,
       price DECIMAL(10, 2) NOT NULL,
       created TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

3. **Configure database credentials**:
   Update the database connection details in `config/Database.php`:
   ```php
   private $host = "localhost";
   private $db_name = "api_db";
   private $username = "root";
   private $password = "";
   ```

4. **Run the API**:
   Start your web server and open the browser or use a tool like Postman to access:
   ```bash
   http://localhost/php-rest-api/api/Product.php
   ```

### Example API Endpoints:
- **GET all products**: `/api/Product.php`
- **POST create new product**: `/api/Product.php`
- **PUT update product**: `/api/Product.php?id={product_id}`
- **DELETE delete product**: `/api/Product.php?id={product_id}`

## License
This project is licensed under the MIT License.
