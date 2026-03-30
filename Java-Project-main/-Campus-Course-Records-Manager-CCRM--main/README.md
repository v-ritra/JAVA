# Campus Course & Records Manager (CCRM)

**Name:** Arka Das  
**Registration Number:** 24BOE10032  
**Course:** Programming in Java  
**Institution:** Vellore Institute of Technology (VIT)

## Table of Contents
- [Project Overview](#project-overview)
- [Evolution of Java](#evolution-of-java)
- [Java Platform Comparison](#java-platform-comparison)
- [Java Architecture](#java-architecture)
- [Installation & Setup](#installation--setup)
- [Project Structure](#project-structure)
- [Features](#features)
- [Technical Implementation](#technical-implementation)
- [How to Run](#how-to-run)
- [Screenshots](#screenshots)
- [Syllabus Mapping](#syllabus-mapping)
- [Sample Usage](#sample-usage)
- [Acknowledgments](#acknowledgments)

## Project Overview

Campus Course & Records Manager (CCRM) is a comprehensive console-based Java SE application designed for educational institutions to efficiently manage:

- **Student Management**: Create, update, enroll/unenroll students in courses
- **Course Management**: Create, update, list, search, and assign instructors to courses
- **Grades & Transcripts**: Record marks, compute GPA, and generate transcripts
- **File Operations**: Import/export CSV data, backup and archive course data

This project demonstrates advanced Java concepts including OOP principles, design patterns, exception handling, NIO.2 file operations, Stream API, and modern Java features.

## Evolution of Java

• **1995**: Java 1.0 - "Write Once, Run Anywhere" philosophy introduced
• **1997**: Java 1.1 - Inner classes, JavaBeans, JDBC introduced
• **1998**: Java 1.2 (J2SE) - Swing, Collections Framework, JIT compiler
• **2000**: Java 1.3 - HotSpot JVM, JNDI included
• **2002**: Java 1.4 - Assert keyword, regular expressions, NIO
• **2004**: Java 5.0 - Generics, annotations, autoboxing, enhanced for-loop
• **2006**: Java 6 - Script engine support, compiler API
• **2011**: Java 7 - Diamond operator, try-with-resources, NIO.2
• **2014**: Java 8 - Lambda expressions, Stream API, Optional class
• **2017**: Java 9 - Module system (Jigsaw), JShell
• **2018**: Java 10 - Local variable type inference (var keyword)
• **2018**: Java 11 LTS - HTTP client, string methods
• **2019**: Java 12-13 - Switch expressions, text blocks preview
• **2020**: Java 14-15 - Pattern matching for instanceof, sealed classes preview
• **2021**: Java 16-17 LTS - Records, sealed classes finalized
• **2022-2024**: Java 18-21 LTS - Virtual threads, pattern matching enhancements

## Java Platform Comparison

| Feature | Java ME (Micro Edition) | Java SE (Standard Edition) | Java EE (Enterprise Edition) |
|---------|------------------------|----------------------------|------------------------------|
| **Target Platform** | Mobile devices, IoT, embedded systems | Desktop applications, standalone apps | Enterprise web applications, servers |
| **Memory Footprint** | Very small (KB to few MB) | Moderate (MB to GB) | Large (GB+) |
| **APIs Included** | Limited subset of Java APIs | Complete Java core APIs | Java SE + Enterprise APIs |
| **Deployment** | Mobile apps, smart cards | Desktop JAR/EXE files | Web servers, application servers |
| **Examples** | Android apps, smart TV apps | Eclipse IDE, NetBeans | Banking systems, e-commerce |
| **Development Focus** | Resource-constrained environments | General-purpose applications | Multi-tier enterprise solutions |

## Java Architecture

### JDK (Java Development Kit)
- **Complete development environment** for Java applications
- **Includes**: JRE + development tools (javac, javadoc, jar, debugger)
- **Used by**: Developers to compile, debug, and package Java applications
- **Size**: Largest component (~100-300 MB)

### JRE (Java Runtime Environment)
- **Runtime environment** required to execute Java applications  
- **Includes**: JVM + core libraries + supporting files
- **Used by**: End users to run Java applications
- **Size**: Medium component (~50-100 MB)

### JVM (Java Virtual Machine)
- **Abstract machine** that provides runtime environment for Java bytecode
- **Responsibility**: Load, verify, and execute Java bytecode
- **Platform-specific**: Different implementations for different operating systems
- **Key features**: Garbage collection, memory management, security

**Interaction Flow:**
Java Source Code (.java) → javac compiler → Bytecode (.class) → JVM → Machine Code


## Installation & Setup

### Windows Java Installation Steps

1. **Download JDK**
   - Visit Oracle JDK download page or OpenJDK
   - Download JDK 11 or higher for Windows x64

2. **Install JDK**
   - Run the installer with administrator privileges
   - Choose installation directory (e.g., `C:\Program Files\Java\jdk-11.0.x`)
   - Complete installation wizard

3. **Set Environment Variables**
JAVA_HOME = C:\Program Files\Java\jdk-11.0.x
PATH = %PATH%;%JAVA_HOME%\bin


4. **Verify Installation**
java -version
javac -version


### Eclipse IDE Setup

1. **Download Eclipse IDE for Java Developers**
2. **Extract and launch Eclipse**
3. **Create New Java Project**:
- File → New → Java Project
- Project name: `CCRM`
- JRE version: Java 11+
- Module settings: Don't create module-info.java

4. **Configure Build Path**:
- Right-click project → Properties → Java Build Path
- Ensure correct JRE is selected

## Features

### Core Functionality
- ✅ **Student Management**: CRUD operations with validation
- ✅ **Course Management**: Advanced search and filtering using Stream API
- ✅ **Enrollment System**: Business rule validation (credit limits, prerequisites)
- ✅ **Grading System**: Automated GPA calculation with enum-based grades
- ✅ **Transcript Generation**: Polymorphic reporting with formatted output
- ✅ **File Operations**: CSV import/export with NIO.2 Path API
- ✅ **Backup System**: Timestamped backups with recursive directory operations

### Advanced Java Features Implemented
- **Design Patterns**: Singleton (AppConfig), Builder (Course creation)
- **Exception Handling**: Custom exceptions with comprehensive error handling
- **Stream API**: Filtering, mapping, and aggregation operations
- **Lambda Expressions**: Functional interfaces for comparisons and predicates  
- **Date/Time API**: Modern temporal handling for all date operations
- **NIO.2**: Path-based file operations with atomic moves and copies
- **Generics**: Type-safe collections and service interfaces
- **Nested Classes**: Static nested classes and inner classes

## Technical Implementation

### OOP Principles Demonstrated

#### Encapsulation
private String studentId; // Private fields

public String getStudentId() { // Public getters
    return studentId;
}

public void setStudentId(String id) { // Validation in setters
    if (id != null && !id.trim().isEmpty()) {
        this.studentId = id;
    }
}



#### Inheritance
// Abstract base class
public abstract class Person {
    protected String id, name, email;
    public abstract String getRole();
}

// Concrete implementations
public class Student extends Person {
    @Override
    public String getRole() {
        return "Student";
    }
}


#### Polymorphism
// Interface-based polymorphism
List<Persistable> services = Arrays.asList(
        new StudentService(),
        new CourseService()
);
services.forEach(service -> {
    try {
        service.save();
    } catch (IOException e) {
        handleException(e);
    }
});


#### Abstraction
// Service interfaces hide implementation complexity
public interface Searchable<T> {
    List<T> search(Predicate<T> criteria);

    default List<T> findByName(String name) {
        return search(item -> item.getName().contains(name));
    }
}


## How to Run

### Prerequisites
- Java JDK 11 or higher
- Eclipse IDE or any Java IDE
- Windows/Linux/macOS

### Compilation & Execution
Clone the repository
```bash
git clone https://github.com/yourusername/-Campus-Course-Records-Manager-CCRM-
```
cd CCRM

Compile (if using command line)
javac -cp src src/edu/ccrm/cli/CCRMApplication.java

Run
java -cp src edu.ccrm.cli.CCRMApplication

Enable assertions (recommended)
java -ea -cp src edu.ccrm.cli.CCRMApplication


### Eclipse IDE
1. Import project: File → Import → Existing Projects into Workspace
2. Right-click `CCRMApplication.java` → Run As → Java Application
3. Follow console menu prompts

## Screenshots

📸 **Screenshot Directory**: `/screenshots/`
- `java-installation.png` - JDK installation verification
<img width="1040" height="241" alt="image" src="https://github.com/user-attachments/assets/a701276e-810a-4a1c-885d-f85c3271a349" />


  
- `eclipse-setup.png` - Eclipse project configuration
<img width="907" height="984" alt="image" src="https://github.com/user-attachments/assets/a1efe1e9-be42-4e3f-99cd-0bcdca51004a" />

  
- `Project Structure.png` - Project Structure
<img width="486" height="607" alt="image" src="https://github.com/user-attachments/assets/4f76f24b-d83f-47d9-883c-b8e72afe2150" />


- `student-management.png` - Student operations demo
<img width="745" height="865" alt="image" src="https://github.com/user-attachments/assets/8c3f4e8f-9dcb-401d-9a26-21ad1badbb3d" />


<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/ebf7d04f-b6a9-4874-8d10-f2967ed9dc34" />


## Syllabus Mapping

| **Syllabus Topic** | **Implementation Location** | **Description** |
|-------------------|----------------------------|-----------------|
| **OOP Principles** | `edu.ccrm.domain.*` | Person hierarchy, encapsulation |
| **Design Patterns** | `AppConfig.java`, `Course.Builder` | Singleton, Builder patterns |
| **Exception Handling** | `edu.ccrm.domain.exceptions.*` | Custom checked/unchecked exceptions |
| **Collections & Generics** | `*Service.java` classes | Type-safe Maps, Lists, Streams |
| **File I/O (NIO.2)** | `edu.ccrm.io.*` | Path API, Files operations |
| **Stream API** | `StudentService.getStatistics()` | Filter, map, reduce operations |
| **Lambda Expressions** | Service search methods | Predicates, comparators |
| **Date/Time API** | Domain classes | LocalDate, DateTimeFormatter |
| **Enums** | `Grade.java`, `Semester.java` | Enum constructors, methods |
| **Nested Classes** | `StudentService.StudentStats` | Static nested class |
| **Interfaces** | `Persistable.java`, `Searchable.java` | Interface inheritance, default methods |
| **Recursion** | `RecursiveUtils.java` | Directory traversal, size calculation |
| **Assertions** | Throughout domain classes | Invariant validation |

## Sample Usage

### Basic Operations
=== CCRM Main Menu ===

Manage Students
Manage Courses
Manage Enrollments
Manage Grades
Import/Export Data
Reports
Backup Data
Exit


Example: Adding a student

Enter choice: 1
Student ID: 24BOE10032 |
Registration Number: 24BOE10032 |
Full Name: Arka Das |
Email: arka.24boe10032@vitbhopal.ac.in

✅ Student added successfully!


### Enabling Assertions
Enable assertions for debugging
java -ea -cp src edu.ccrm.cli.CCRMApplication

Assertions validate business rules:
assert studentId != null : "Student ID cannot be null";
assert credits >= 1 && credits <= 6 : "Credits must be between 1-6";


## Error Handling

The application implements robust exception handling:

### Errors vs Exceptions
- **Errors**: System-level problems (OutOfMemoryError, StackOverflowError)
- **Exceptions**: Recoverable conditions handled by application logic

### Custom Exception Examples
// Checked exceptions for business rule violations
public class MaxCreditLimitExceededException extends Exception {
    public MaxCreditLimitExceededException(String message) {
        super(message);
    }
}

// Unchecked exceptions for programming errors
public class DuplicateEnrollmentException extends RuntimeException {
    public DuplicateEnrollmentException(String message) {
        super(message);
    }
}


## Acknowledgments

- **Java Documentation**: Oracle official Java tutorials and documentation
- **Design Patterns**: Gang of Four Design Patterns reference
- **Stream API**: Java 8 functional programming concepts
- **NIO.2**: Modern Java I/O best practices

---

**Project Completed**: November 2025  
**Academic Session**: Semester 4, B.Tech Computer Science  
**Institution**: Vellore Institute of Technology (VIT)

*This project demonstrates comprehensive understanding of Java SE features, object-oriented programming principles, and software engineering best practices.*
