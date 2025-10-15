# Hospital Management System (Java & MySQL)
The Hospital Management System is a simple command-line application designed to manage patients, doctors, and appointments using Java and MySQL. It demonstrates basic CRUD operations, database connectivity, and interaction between Java and MySQL. This project serves as a learning tool for understanding the integration of Java with MySQL.

# **Features**

Add Patients: Allows adding patient details to the database.

View Patients: Displays a list of all patients stored in the database.

View Doctors: Displays a list of all doctors stored in the database.

Book Appointments: Enables booking an appointment between a patient and a doctor, ensuring the doctor's availability on the specified date.

Exit: Closes the application and database connection safely.


# **Technologies Used**

Programming Language: Java

Database: MySQL

IDE: Visual Studio Code (VS Code)

JDBC Driver: MySQL Connector/J


# **Prerequisites**

Java Development Kit (JDK): Ensure JDK is installed and configured.

MySQL Server: Installed and running with access to MySQL Workbench or Shell.

MySQL JDBC Driver: Add the MySQL Connector/J .jar file to your project.

Database Setup: Create the required database and tables.


# **Database Setup**

```sql
-- Cell 1: Create Database
CREATE DATABASE hospital;
```

-- Cell 2: Use Database
USE hospital;

-- Cell 3: Create Patients Table
CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
);

-- Cell 4: Create Doctors Table
CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    specialization VARCHAR(255),
    contact_info VARCHAR(255)
);

-- Cell 5: Create Appointments Table
CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT,
    doctor_id INT,
    appointment_date DATETIME,
    status VARCHAR(50),
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);


# **How to Run**

Clone or Download the Project.

Add MySQL Connector/J:

Place the .jar file in a lib folder in your project directory.

Add the .jar file to the project classpath.


# **Update Database Credentials:**

Modify the following fields in the HospitalManagement class:

private static final String url = "jdbc:mysql://localhost:3306/hospital";

private static final String username = "your_mysql_username";

private static final String password = "your_mysql_password";


# **Compile and Run:**

javac -cp ".;lib/mysql-connector-j-9.1.0.jar" src/*.java

java -cp ".;lib/mysql-connector-j-9.1.0.jar;src" HospitalManagement


