Java Web Application – Login System

This is a simple Java web application built from scratch without frameworks (e.g., Spring Boot). It demonstrates a login page where a user can authenticate against a MySQL database and view a personalized welcome message.

Features

Login page with username/password authentication

Validation against MySQL database

Displays personalized welcome message with user data

Runs locally on Tomcat server

Deployable to AWS Elastic Beanstalk (WAR file) with RDS MySQL backend

Prerequisites

Java JDK 8+

Eclipse IDE (or any Java IDE)

Apache Tomcat 9+

MySQL Server (local or AWS RDS)

Maven (for build management)

AWS Account (for cloud deployment)

Project Structure
java-webapp/
 ├── src/
 │   └── main/
 │       └── java/
 │           └── com.example.webapp/
 │               ├── LoginServlet.java
 │               └── DatabaseConnection.java
 ├── WebContent/ (or src/main/webapp for Maven)
 │   ├── index.jsp
 │   ├── login.jsp
 │   └── welcome.jsp
 ├── pom.xml
 └── README.md

Database Setup

Start MySQL server (local or RDS).

Create a database and table:

CREATE DATABASE webappdb;

USE webappdb;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(50) NOT NULL,
    fullname VARCHAR(100) NOT NULL
);

INSERT INTO users (username, password, fullname)
VALUES ('Username', 'Password', 'Full Name');


Update your DatabaseConnection.java with correct DB credentials.

Running Locally

Import into Eclipse (as Maven project).

Configure Tomcat server in Eclipse.

Deploy and run the project.

Open in browser:

http://localhost:8080/java-webapp/login.jsp

AWS Deployment

Package the project:

mvn clean package


This generates a WAR file in target/.

Upload WAR file to AWS Elastic Beanstalk (Tomcat environment).

Configure an RDS MySQL instance and update connection string.

Access the app via your Elastic Beanstalk URL:

AWS Link

Example Login

Username: User

Password: Password

After login, you should see:

Welcome, User!
Login successful for user: User

Future Improvements

Password hashing (e.g., BCrypt)

User session management

Role-based access control

Logging & monitoring

Dockerize for portability
