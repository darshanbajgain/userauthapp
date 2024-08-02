# User Authentication Backend
This is a Spring Boot application for basic  user authentication (not secure, no  use of spring security), including registration and login functionalities.

## Folder Structure
```src
|-- main
|   |-- java
|   |   |-- com
|   |   |   |-- darshan
|   |   |   |   |-- userauth
|   |   |   |   |   |-- controller
|   |   |   |   |   |   `-- UserController.java
|   |   |   |   |   |-- entity
|   |   |   |   |   |   `-- User.java
|   |   |   |   |   |-- repository
|   |   |   |   |   |   `-- UserRepository.java
|   |   |   |   |   `-- service
|   |   |   |   |       `-- UserService.java
|   |   |   |   `-- UserAuthApplication.java
|   |-- resources
|       |-- static
|       |-- templates
|       `-- application.properties
|-- test
```


## Prerequisites
Java 17
Maven
MySQL

## Setup
### 1. Clone the Repository

```git clone https://github.com/darshanbajgain/user-auth.git```

```cd user-auth```

### 2. Configure the Database
Create a MySQL database for the project. You can use the MySQL command line or a GUI tool like My.

```sql
CREATE DATABASE userauthdb;
```
### 3. Update application.properties
Edit the src/main/resources/application.properties file to set your MySQL username and password.

```
spring.application.name=userauth
spring.datasource.url=jdbc:mysql://localhost:3306/userauthdb
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```

### 4. Install Dependencies
Navigate to the project root directory and run the following command to install all necessary dependencies.

```mvn clean install```

### 5. Run the Application
Start the application using Maven.

```mvn spring-boot:run```
The application will be running at http://localhost:8080.

### API Endpoints
**Register User**
URL: /api/user/register
Method: POST
Payload:
```json
{
  "username": "your_username",
  "password": "your_password",
  "email": "your_email"
}
```

**Login User**
URL: /api/user/login
Method: POST
Payload:
```json
{
  "username": "your_username",
  "password": "your_password"
}
```

### Dependencies
Ensure you have the following dependencies in your pom.xml:

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-data-jpa</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
    <dependency>
        <groupId>com.mysql</groupId>
        <artifactId>mysql-connector-j</artifactId>
        <scope>runtime</scope>
    </dependency>
    <dependency>
        <groupId>org.projectlombok</groupId>
        <artifactId>lombok</artifactId>
        <optional>true</optional>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.springframework.security</groupId>
        <artifactId>spring-security-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```
### Creating the Database
To create the database, ensure MySQL is running, and execute the following command in your MySQL console:

```sql
CREATE DATABASE userauthdb;
```
Then, update your application.properties with your MySQL username and password as shown above.

### Running MySQL
Start the MySQL service:

**On Linux:**
```bash
sudo service mysql start
```
**On Windows:**
```bash
net start MySQL
```

**On macOS:**
```bash
brew services start mysql
```

### Conclusion
You should now be able to run the application and interact with the user authentication endpoints. Feel free to contribute to this project or report any issues.

