# ddd-cargo

[![zh-CN](https://img.shields.io/badge/lang-zh--CN-red.svg)](https://github.com/Argentum11/ddd-cargo/blob/master/README.zh-CN.md)

Domain-Driven Cargo Demand Example

## Requirements - Excerpt from Chapter 7 of "Domain-Driven Design"

Assume we are developing new software for a cargo company. The initial requirements include three basic functions:

1. Pre-booking cargo
2. Tracking the main processing flow of customer cargo
3. Automatically sending invoices to customers when the cargo reaches a certain point in its processing.

## DDD, CQRS Architecture Diagram

![Architecture Diagram](./ddd.png)

## DDD, CQRS Code Structure

![Code Structure](./ddd_package.png)

## Example

The ddd-cargo-example is a single Maven module project, an implementation example of DDD + CQRS, developed based on Spring Boot.

Next, we will use the ddd-cargo-example to demonstrate how to implement it.

1. Modify the database connection in `/ddd-cargo-example/src/main/resources/application.properties`

```SQL
spring.datasource.
url=jdbc:mysql://127.0.0.1:MySQL_PORT/ddd-sayi-db?useUnicode=true&characterEncoding=UTF-8
spring.datasource.username=USER_NAME
spring.datasource.password=USER_PASSWORD
```

2. Initialize the database using the script file /ddd-cargo-example/mysql_init.sql.

    a. login mysql

    ```bash
     mysql -u root -p
     ```

    b. create database manually using SQL

    ```bash
    CREATE DATABASE `ddd-sayi-db`;
    use `ddd-sayi-db`;
    source /ddd-cargo-example/mysql_init.sql
    ```

3. run `/ddd-cargo-example/src/main/java/com/deepoove/cargo/CargoApplication.java`
  
  ```bash
  mvn clean install
  java -jar target/ddd-cargo-example-0.0.1-SNAPSHOT.jar

  ```

4. Access [Cargo Admin](http://127.0.0.1:8077/index.html) via your browser.

### Query Cargo

![Query Cargo](./cargo_home.png)

### Book Cargo

![Book Cargo](./cargo_book.png)

### Cargo event

![Cargo event](./cargo_event.png)

### Track Cargo

![Track Cargo](./cargo_track.png)

## Article

[Evoopeed：领域驱动设计DDD和CQRS落地](https://mp.weixin.qq.com/s/R-jBnPhWJHs7J-4CETV88A)
