# IT2234P Web Services and Server Technologies

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Code Quality](https://img.shields.io/badge/Code%20Quality-A-brightgreen?style=for-the-badge)]())

> 📚 A comprehensive collection of daily practical lessons for Web Services and Server Technologies course.

## 📋 Course Overview

This repository serves as a practical guide through various web services and server technologies. Each lesson is organized in dedicated folders containing both source code and visual outputs.

## 🗓️ Latest Session: Student Management REST API Implementation

### 🎯 Learning Objectives

- Build a RESTful API using Express.js and Node.js
- Implement CRUD operations for student data management
- Create efficient routing and service layers
- Develop search and filter functionalities
- Implement sorting and pagination features
- Handle API responses and error cases
- Structure the application using modular components
- Test API endpoints using Postman

### 💻 Code Structure & Implementation

#### 1. Core Components

##### Server Configuration (`index.js`)
- Express.js server setup
- Middleware configuration
- Route integration
- Error handling

##### Data Layer (`studentsdb.js`)
```javascript
let students = [
    {regno:'2020ict32',name:'anushika',gender:'f',age:'25',course:'ICT'},
    {regno:'2020ict125',name:'wenura',gender:'m',age:'25',course:'ICT'},
    // More student records...
];
```

##### Service Layer (`studentservice.js`)
```javascript
function getStudents() {
    return students;
}

function getStudentById(id) {
    return students.find(student => student.regno == id);
}
```

#### 2. API Endpoints

##### Student Routes (`studentroute.js`)
- GET `/students` - Retrieve all students
- GET `/students/search?name={query}` - Search students by name
- GET `/students/filter` - Filter students by various criteria
- GET `/students/sort` - Sort and paginate results
- GET `/students/{id}` - Get student by ID

### 📊 Implementation Summary

| Category | Endpoint | Description | Output |
|----------|----------|-------------|--------|
| Basic Operations | `GET /students` | Retrieve all students | [View](outputs/Get%20All%20Students.png) |
| Search | `GET /students/search` | Search by student name | [View](outputs/Search%20Students%20by%20Name.png) |
| Filtering | `GET /students/filter?age=25` | Filter by age | [View](outputs/Filter%20Students%20by%20Age.png) |
| Filtering | `GET /students/filter?gender=f` | Filter by gender | [View](outputs/Filter%20Students%20by%20Gender.png) |
| Filtering | `GET /students/filter?course=ICT` | Filter by course | [View](outputs/Filter%20Students%20by%20Course.png) |
| Advanced Filtering | `GET /students/filter?age=25&course=ICT` | Combined filters | [View](outputs/Combined%20Filters%20Age%20and%20Course.png) |
| Sorting & Pagination | `GET /students/sort?field=age&order=asc` | Sort by age ascending | [View](outputs/Sort%20and%20Limit%20Results%20Sort%20by%20age%20(ascending).png) |
| Sorting & Pagination | `GET /students/sort?field=name&order=desc&limit=3` | Sort by name with limit | [View](outputs/Sort%20and%20Limit%20Results%20Sort%20by%20name%20(descending)%20with%20limit.png) |
| Individual Records | `GET /students/:id` | Get student by ID | [View](outputs/Get%20Student%20by%20ID.png) |

### 🔍 Technical Notes

- Built with Express.js and Node.js
- Modular architecture with separate routing and service layers
- Comprehensive error handling
- Flexible filtering and sorting capabilities
- Documented API endpoints with example responses
- Postman collection for API testing

---

<div align="center">

📖 **API Documentation** | 🛠️ **Implementation Details** | 📊 **Test Results**

</div>