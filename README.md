# IT2234P Web Services and Server Technologies

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![RESTful API](https://img.shields.io/badge/RESTful-API-blue?style=for-the-badge)]()

> 📚 A Student API project demonstrating RESTful web services using Node.js and Express.

## 📋 Project Overview

This repository contains a Student API implementation that demonstrates RESTful web services using Node.js and Express. The project includes a complete backend system for managing student data with various endpoints for retrieving, filtering, and sorting student information.

## 🗓️ Latest Session: Student API Implementation (April 7, 2025)

### 🎯 Learning Objectives

- Implement a RESTful API using Express.js
- Create routes for data retrieval and filtering
- Develop service layers for data access
- Implement query parameter handling
- Design effective API response formats
- Test API endpoints using Postman
- Implement sorting and pagination functionality
- Create combined filtering capabilities

### 💻 Project Structure

```
Code/
├── index.js                # Main server entry point
├── package.json            # Project dependencies
├── student/
│   ├── server.js           # (Deprecated) Previous server implementation
│   ├── studentroute.js     # API route definitions
│   ├── studentsdb.js       # Student data storage
│   ├── studentservice.js   # Service layer for data access
│   └── postman_guide.md    # Documentation for API testing
```

### 🚀 API Endpoints

#### 1. Get All Students
- **Method**: GET
- **URL**: `/students`
- **Description**: Retrieves a list of all students from the database
- **Example**: [View Output](Output/Get%20All%20Students.png)

#### 2. Get Student by ID
- **Method**: GET
- **URL**: `/students/:id`
- **Description**: Finds a specific student using their ID number
- **Example**: [View Output](Output/Get%20Student%20by%20ID.png)

#### 3. Search Students by Name
- **Method**: GET
- **URL**: `/students/search?name=query`
- **Description**: Searches for students by their name
- **Example**: [View Output](Output/Search%20Students%20by%20Name.png)

#### 4. Filter Students by Age
- **Method**: GET
- **URL**: `/students/filter?age=value`
- **Description**: Filters students by their age
- **Example**: [View Output](Output/Filter%20Students%20by%20Age.png)

#### 5. Filter Students by Course
- **Method**: GET
- **URL**: `/students/filter?course=value`
- **Description**: Filters students by their enrolled course
- **Example**: [View Output](Output/Filter%20Students%20by%20Course.png)

#### 6. Filter Students by Gender
- **Method**: GET
- **URL**: `/students/filter?gender=value`
- **Description**: Filters students by their gender
- **Example**: [View Output](Output/Filter%20Students%20by%20Gender.png)

#### 7. Combined Filters
- **Method**: GET
- **URL**: `/students/filter?param1=value1&param2=value2`
- **Description**: Filter students using multiple criteria
- **Example**: [View Output](Output/Combined%20Filters%20Age%20and%20Course.png)

#### 8. Sort and Limit Results
- **Method**: GET
- **URL**: `/students?sort=field&order=direction&limit=number`
- **Description**: Get students with sorting and limiting options
- **Examples**: 
  - [Sort by age (ascending)](Output/Sort%20and%20Limit%20Results%20Sort%20by%20age%20(ascending).png)
  - [Sort by name (descending) with limit](Output/Sort%20and%20Limit%20Results%20Sort%20by%20name%20(descending)%20with%20limit.png)

### 📊 Implementation Details

#### Student Data Structure

```javascript
// Sample student object
{
  regno: '2020ict32',  // Registration number (unique ID)
  name: 'anushika',    // Student name
  gender: 'f',         // Gender (m/f)
  age: '25',           // Age
  course: 'ICT'        // Course enrolled
}
```

#### Server Implementation

The API server is implemented using Express.js with the following components:

- **index.js**: Main server entry point that configures Express and routes
- **studentroute.js**: Defines all API endpoints and request handling logic
- **studentsdb.js**: Contains the student data (simulated database)
- **studentservice.js**: Service layer that provides data access methods

### 🔍 Technical Notes

- The API follows RESTful design principles
- Query parameters are used for filtering and sorting
- Route parameters are used for resource identification
- Appropriate HTTP status codes are returned for success and error cases
- The API includes comprehensive error handling
- Documentation is provided for testing with Postman

### 📊 Implementation Summary

| Category | File | Description | Output |
|----------|------|-------------|--------|
| Server Setup | `index.js` | Main server configuration and initialization | - |
| API Routes | `studentroute.js` | API endpoint definitions and request handling | [View All Students](Output/Get%20All%20Students.png) |
| Data Storage | `studentsdb.js` | Student data management and storage | - |
| Service Layer | `studentservice.js` | Business logic and data access methods | - |
| Documentation | `postman_guide.md` | API testing and usage documentation | - |
| Search Operations | `studentroute.js` | Name-based student search implementation | [View Search](Output/Search%20Students%20by%20Name.png) |
| Filter Operations | `studentroute.js` | Multi-criteria student filtering | [View Filters](Output/Combined%20Filters%20Age%20and%20Course.png) |
| Sort Operations | `studentroute.js` | Student data sorting and pagination | [View Sorting](Output/Sort%20and%20Limit%20Results%20Sort%20by%20age%20(ascending).png) |

---

<div align="center">

📖 **RESTful API** | 🛠️ **Express.js** | 📊 **Student Data Management**

</div>