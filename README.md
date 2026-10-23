# Inventory Management System

## About the Project

The Inventory Management System is a web application developed using ASP.NET MVC, C#, ADO.NET, and SQL Server.

It allows users to manage product information efficiently by performing Create, Read, Update, and Delete (CRUD) operations.

## Features

* **Add Product:** Add new products to the inventory.
* **View Products:** Display all products with their details.
* **Update Product:** Edit existing product information.
* **Delete Product:** Remove products from the inventory.
* **Database Integration:** Store and manage product data using SQL Server.

## Technologies Used

* ASP.NET MVC 5
* C#
* ADO.NET
* Microsoft SQL Server
* HTML
* Razor View Engine
* Visual Studio 2022

## Project Structure

```text
InventoryManagement/
├── Controllers/
│   └── ProductsController.cs
├── Models/
│   └── Product.cs
├── Views/
│   └── Products/
│       ├── Index.cshtml
│       ├── Create.cshtml
│       ├── Edit.cshtml
│       └── Delete.cshtml
├── App_Start/
│   └── RouteConfig.cs
├── Web.config
└── README.md
```

## Database Setup

### 1. Create the Database

Open SQL Server Management Studio and execute:

```sql
CREATE DATABASE InventoryDB;
GO

USE InventoryDB;
GO
```

### 2. Create the Products Table

```sql
CREATE TABLE Products
(
    ProductId INT PRIMARY KEY IDENTITY(1,1),
    ProductName VARCHAR(100) NOT NULL,
    Quantity INT NOT NULL,
    Price DECIMAL(10,2) NOT NULL
);
GO
```

### 3. Insert Sample Data

```sql
INSERT INTO Products (ProductName, Quantity, Price)
VALUES
('Keyboard', 20, 500.00),
('Mouse', 30, 250.00),
('Monitor', 10, 7500.00);
GO
```

## Database Connection

The application connects to SQL Server LocalDB using the following connection string in `ProductsController.cs`:

```csharp
private string connectionString =
    @"Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=InventoryDB;Integrated Security=True";
```

Ensure that SQL Server LocalDB is installed and the `InventoryDB` database exists.

## How to Run the Project

1. Install Visual Studio 2022.
2. Ensure the ASP.NET Web Application (.NET Framework) workload and .NET Framework targeting pack are available.
3. Install SQL Server LocalDB.
4. Create the `InventoryDB` database and `Products` table using the SQL scripts above.
5. Open `InventoryManagement.sln` in Visual Studio.
6. Build the solution.
7. Run the application using **F5**.
8. Navigate to `/Products/Index` if the inventory page does not open automatically.

## CRUD Operations

| Operation | Description             | SQL Command |
| --------- | ----------------------- | ----------- |
| Create    | Add a new product       | INSERT      |
| Read      | Display product records | SELECT      |
| Update    | Modify product details  | UPDATE      |
| Delete    | Remove a product        | DELETE      |

## Learning Outcomes

* Understanding the MVC architecture.
* Connecting a C# application to SQL Server using ADO.NET.
* Executing SQL queries using `SqlConnection` and `SqlCommand`.
* Reading database records using `SqlDataReader`.
* Implementing CRUD operations in an ASP.NET MVC application.

## Conclusion

The Inventory Management System demonstrates how ASP.NET MVC and ADO.NET can be used to develop a database-driven web application. It provides basic functionality for managing product information through CRUD operations.
