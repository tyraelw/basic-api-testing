# Basic API Testing Practice

A foundational API testing collection demonstrating essential testing patterns and validation techniques using Postman and the JSONPlaceholder API.

## 📋 Project Overview

This project showcases fundamental API testing concepts including GET and POST requests, response validation, query parameter usage, and basic assertion patterns. It demonstrates core RESTful API testing techniques that form the foundation for more complex testing scenarios.

## 🎯 Skills Demonstrated

This collection demonstrates proficiency in:

- **Testing REST API endpoints** using GET and POST methods
- **Validating HTTP status codes** (200, 201) for different operations
- **Parsing and validating JSON responses** using Postman test scripts
- **Verifying data types** (arrays, objects, strings)
- **Using query parameters** to filter API responses
- **Validating object properties** exist and contain expected values
- **Checking data format** (email validation, URL protocol verification)
- **Iterating through arrays** to validate multiple items
- **Writing clear, maintainable test assertions** in JavaScript

## 📊 Test Coverage

### Endpoints Tested

| Endpoint | Method | Tests | Purpose |
|----------|--------|-------|---------|
| `/posts` | GET | 3 | Retrieve all posts, validate array response |
| `/posts/1` | GET | 4 | Get single post, verify required fields |
| `/posts?userId=1` | GET | 3 | Filter posts by user, validate query params |
| `/posts` | POST | 3 | Create new post, validate creation response |
| `/users` | GET | 3 | Get all users, verify data presence |
| `/users/1` | GET | 4 | Get single user, validate email format |
| `/comments` | GET | 3 | Get all comments, verify structure |
| `/comments?postId=1` | GET | 3 | Filter comments, validate filtering |
| `/albums` | GET | 3 | Get all albums, verify response |
| `/photos/1` | GET | 5 | Get photo, validate URLs and fields |

**Total: 10 requests with 34 automated tests**

## 🛠️ Technologies Used

- **Postman** - API testing platform
- **JSONPlaceholder** - Free REST API for testing
- **JavaScript** - Test scripting language
- **JSON** - Data format

## 📝 Key Testing Patterns

### Status Code Validation
```javascript
pm.test("Status code is 200", function() {
    pm.response.to.have.status(200);
});
```

### Response Type Validation
```javascript
pm.test("Response is an array", function() {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.be.an('array');
});
```

### Property Existence Check
```javascript
pm.test("Post has title", function() {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.exist;
});
```

### Array Iteration and Validation
```javascript
pm.test("All posts belong to user 1", function() {
    var jsonData = pm.response.json();
    jsonData.forEach(function(post) {
        pm.expect(post.userId).to.equal(1);
    });
});
```

### String Content Validation
```javascript
pm.test("Email is valid format", function() {
    var jsonData = pm.response.json();
    pm.expect(jsonData.email).to.include("@");
});
```

## 🚀 How to Run

### Prerequisites
- Postman installed ([Download here](https://www.postman.com/downloads/))

### Steps
1. Download the `basic-api-testing.postman_collection.json` file
2. Open Postman
3. Click **Import** button
4. Select the downloaded file
5. The collection will appear in your Collections sidebar

### Running Tests

**Option 1: Run Individual Requests**
- Click on any request
- Click **Send** button
- View test results in the **Test Results** tab

**Option 2: Run Entire Collection**
- Right-click on the collection name
- Select **Run collection**
- Click **Run Basic API Testing Practice**
- View all test results in the runner

### Expected Results
```
✓ All 10 requests should pass
✓ All 34 tests should pass
✓ Average response time: < 500ms
```

## 📈 Test Results Summary

All tests validate:
- ✅ Correct HTTP status codes
- ✅ Response data types and structures
- ✅ Required fields are present
- ✅ Data filtering works correctly
- ✅ Data formats are valid (emails, URLs)

## 🎓 Skills Demonstrated

### API Testing Fundamentals
- Understanding RESTful API concepts
- Working with different HTTP methods (GET, POST)
- Interpreting HTTP status codes

### Postman Proficiency
- Creating and organizing API requests
- Writing automated test scripts
- Using Postman's test assertion library

### JavaScript Knowledge
- Variable declaration and manipulation
- Array iteration with `forEach`
- Object property access
- Conditional logic in tests

### Quality Assurance Mindset
- Comprehensive test coverage
- Clear test naming conventions
- Validation of multiple scenarios
- Edge case consideration

## 🔗 Related Projects

- [API Intermediate Testing](../api-intermediate-testing) - Advanced patterns with variable chaining and full CRUD
- [Trello API Testing](../trello-api-testing) - Production-level API testing with authentication
- [Simple Grocery Store API](../simple-grocery-store-api-testing) - E-commerce flow testing

## 📌 Portfolio Context

This project is part of a structured portfolio demonstrating comprehensive API testing knowledge from fundamental concepts to advanced implementations. While my advanced projects showcase production-ready patterns like [complete CRUD workflows with authentication](../trello-api-testing), this collection focuses on clearly demonstrating core API testing concepts that underpin those complex implementations.

**Focus Area:** Fundamental API testing patterns
- GET and POST request validation
- Response structure verification
- Basic assertion patterns
- Query parameter usage

**Related Skill Levels:**
- **Intermediate:** [API Intermediate Testing](../api-intermediate-testing) - Variable chaining, pre-request scripts, full CRUD
- **Advanced:** [Trello API Testing](../trello-api-testing) - Authentication, Newman CLI, CI/CD integration

## 📝 Notes

- **API Used**: JSONPlaceholder is a free fake REST API for testing and prototyping
- **Purpose**: Demonstrates understanding of fundamental API testing concepts
- **Test Data**: Uses publicly available test data from JSONPlaceholder
- **No Authentication**: This API doesn't require authentication, allowing focus on core testing patterns

## 📧 Contact

For questions about this project or API testing best practices, feel free to reach out via [tyrael78w@gmail.com](mailto:tyrael78w@gmail.com)

---

**Part of QA Testing Portfolio** | **November 2025**

