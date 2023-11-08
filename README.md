# whole-project-data
CREATE TABLE Product (
    ProductID NUMBER PRIMARY KEY,
    ProductName VARCHAR2(255),
    Description VARCHAR2(1000),
    Price NUMBER(10, 2),
    StockQuantity NUMBER
);
/
CREATE TABLE ProductCategory (
    CategoryID NUMBER PRIMARY KEY,
    CategoryName VARCHAR2(255),
    ParentCategoryID NUMBER,
    Description VARCHAR2(1000)
);
/
CREATE TABLE Supplier (
    SupplierID NUMBER PRIMARY KEY,
    SupplierName VARCHAR2(255),
    ContactName VARCHAR2(255),
    ContactEmail VARCHAR2(255),
    Phone VARCHAR2(20),
    Address VARCHAR2(255),
    City VARCHAR2(100),
    State VARCHAR2(50),
    PostalCode VARCHAR2(20),
    Country VARCHAR2(100)
);
/
CREATE TABLE ProductSupplier (
    ProductID NUMBER,
    SupplierID NUMBER,
    PRIMARY KEY (ProductID, SupplierID),
    FOREIGN KEY (ProductID) REFERENCES Product(ProductID),
    FOREIGN KEY (SupplierID) REFERENCES Supplier(SupplierID)
);
/
CREATE TABLE Customer (
    CustomerID NUMBER PRIMARY KEY,
    FirstName VARCHAR2(255),
    LastName VARCHAR2(255),
    Email VARCHAR2(255),
    Phone VARCHAR2(20),
    Address VARCHAR2(255),
    City VARCHAR2(100),
    State VARCHAR2(50),
    PostalCode VARCHAR2(20),
    Country VARCHAR2(100)
);
/
CREATE TABLE Location (
    LocationID NUMBER PRIMARY KEY,
    LocationName VARCHAR2(255),
    Address VARCHAR2(255),
    City VARCHAR2(100),
    State VARCHAR2(50),
    PostalCode VARCHAR2(20),
    Country VARCHAR2(100)
);
/
CREATE TABLE PurchaseOrder (
    OrderID NUMBER PRIMARY KEY,
    SupplierID NUMBER,
    OrderDate DATE,
    TotalAmount NUMBER(10, 2),
    Status VARCHAR2(50)
);
/
CREATE TABLE SalesOrder (
    OrderID NUMBER PRIMARY KEY,
    CustomerID NUMBER,
    OrderDate DATE,
    TotalAmount NUMBER(10, 2),
    Status VARCHAR2(50)
);
/
CREATE TABLE SalesOrderDetails (
    OrderDetailID NUMBER PRIMARY KEY,
    OrderID NUMBER,
    ProductID NUMBER,
    Quantity NUMBER,
    UnitPrice NUMBER(10, 2),
    TotalAmount NUMBER(10, 2)
);
/
