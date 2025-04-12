# Using Postman to Test Student API

## Testing Student API Endpoints

### Base URL
```
http://127.0.0.1:3000
```

### Available Endpoints

#### 1. Get All Students
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students
- **Description**: Retrieves a list of all students from the database
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Enter the URL: http://127.0.0.1:3000/students
  4. Click 'Send'
- **Expected Response**:
  - Success (200): A list of student objects
  - Error (404): "Sorry!, Student not found"

#### 2. Get Student by ID
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/:id
- **Description**: Finds a specific student using their ID number
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Replace ':id' with an actual student ID (e.g., http://127.0.0.1:3000/students/12345)
  4. Click 'Send'
- **Expected Response**:
  - Success (200): A single student object
  - Error (404): "Sorry!, Student not found"

#### 3. Search Students by Name
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/search
- **Description**: Searches for students by their name
- **Query Parameters**: name (string, required)
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Enter URL with query: http://127.0.0.1:3000/students/search?name=John
  4. Click 'Send'
- **Expected Response**:
  - Success (200): List of students matching the search criteria
  - Error (400): "Please provide a name to search"
  - Error (404): "No students found with name containing '[name]'"

#### 4. Filter Students by Age
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/filter
- **Description**: Filters students by their age
- **Query Parameters**: age (number, required)
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Enter URL with query: http://127.0.0.1:3000/students/filter?age=15
  4. Click 'Send'
- **Expected Response**:
  - Success (200): List of students matching the age criteria
  - Error (400): "Please provide a valid age number"
  - Error (404): "No students found with age [age]"

#### 5. Filter Students by Course
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/filter
- **Description**: Filters students by their enrolled course
- **Query Parameters**: course (string, required)
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Enter URL with query: http://127.0.0.1:3000/students/filter?course=math
  4. Click 'Send'
- **Expected Response**:
  - Success (200): List of students enrolled in the specified course
  - Error (400): "Please provide a course name"
  - Error (404): "No students found in course [course]"

#### 6. Filter Students by Gender
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/filter
- **Description**: Filters students by their gender
- **Query Parameters**: gender (string, required)
- **Steps**:
  1. Open Postman
  2. Select 'GET' from the dropdown
  3. Enter URL with query: http://127.0.0.1:3000/students/filter?gender=f
  4. Click 'Send'
- **Expected Response**:
  - Success (200): List of students matching the gender criteria
  - Error (400): "Please provide a gender"
  - Error (404): "No students found with gender [gender]"

#### 7. Combined Filters
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students/filter
- **Description**: Filter students using multiple criteria
- **Query Parameters**: Combine any of the following:
  - age (number)
  - course (string)
  - gender (string)
- **Example Combinations**:
  1. Age and Course:
     - URL: http://127.0.0.1:3000/students/filter?age=15&course=math
     - Response: Students aged 15 enrolled in math
  2. Course and Gender:
     - URL: http://127.0.0.1:3000/students/filter?course=science&gender=f
     - Response: Female students enrolled in science
  3. Age and Gender:
     - URL: http://127.0.0.1:3000/students/filter?age=16&gender=m
     - Response: Male students aged 16
  4. All Filters:
     - URL: http://127.0.0.1:3000/students/filter?age=15&course=math&gender=f
     - Response: Female students aged 15 enrolled in math
- **Expected Response**:
  - Success (200): List of students matching all specified criteria
  - Error (400): "Invalid filter parameters"
  - Error (404): "No students found matching the specified criteria"

#### 8. Sort and Limit Results
- **Method**: GET
- **URL**: http://127.0.0.1:3000/students
- **Description**: Get students with sorting and limiting options
- **Query Parameters**:
  - sort (string): Field to sort by (name, age)
  - order (string): Sort order (asc, desc)
  - limit (number): Maximum number of results
- **Example Queries**:
  1. Sort by age (ascending):
     - URL: http://127.0.0.1:3000/students?sort=age&order=asc
  2. Sort by name (descending) with limit:
     - URL: http://127.0.0.1:3000/students?sort=name&order=desc&limit=10
- **Expected Response**:
  - Success (200): Sorted and limited list of students
  - Error (400): "Invalid sort parameters"

### Example Response Formats

#### Success Response (200)
```json
{
  "status": "success",
  "count": 2,
  "data": [
    {
      "id": "12345",
      "name": "John Doe",
      "age": 15,
      "gender": "m",
      "course": "math"
    },
    {
      "id": "12346",
      "name": "Jane Smith",
      "age": 16,
      "gender": "f",
      "course": "science"
    }
  ]
}
```

#### Error Response (400)
```json
{
  "status": "error",
  "message": "Invalid filter parameters"
}
```