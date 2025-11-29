# 🔍 Basic API Testing Practice
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black) ![API Testing](https://img.shields.io/badge/API-Testing-blue)

A foundational API testing collection demonstrating essential testing patterns and validation techniques using Postman and the JSONPlaceholder API.

## 📋 Project Overview

This project showcases fundamental API testing concepts including GET and POST requests, response validation, query parameter usage, and basic assertion patterns. It demonstrates core RESTful API testing techniques that form the foundation for more complex testing scenarios.

## 📊 Test Coverage

### Endpoints Tested

| Endpoint | Method | Tests | Purpose |
|----------|--------|-------|---------|
| /posts | GET | 3 | Retrieve all posts, validate array response |
| /posts/1 | GET | 4 | Get single post, verify required fields |
| /posts?userId=1 | GET | 3 | Filter posts by user, validate query params |
| /posts | POST | 3 | Create new post, validate creation response |
| /users | GET | 3 | Get all users, verify data presence |
| /users/1 | GET | 4 | Get single user, validate email format |
| /comments | GET | 3 | Get all comments, verify structure |
| /comments?postId=1 | GET | 3 | Filter comments, validate filtering |
| /albums | GET | 3 | Get all albums, verify response |
| /photos/1 | GET | 5 | Get photo, validate URLs and fields |

**Total:** 10 requests with 34 automated tests

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

1. Click on any request
2. Click **Send** button
3. View test results in the **Test Results** tab

**Option 2: Run Entire Collection**

1. Right-click on the collection name
2. Select **Run collection**
3. Click **Run Basic API Testing Practice**
4. View all test results in the runner

### Expected Results

- ✓ All 10 requests should pass
- ✓ All 34 tests should pass
- ✓ Average response time: < 500ms

## 📈 Test Results Summary

All tests validate:

- ✅ Correct HTTP status codes
- ✅ Response data types and structures
- ✅ Required fields are present
- ✅ Data filtering works correctly
- ✅ Data formats are valid (emails, URLs)

## 🎯 Skills Demonstrated

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

## 📝 Notes

- **API Used:** JSONPlaceholder - Free fake REST API for testing and prototyping
- **Test Data:** Uses publicly available test data from JSONPlaceholder
- **Authentication:** Not required (focuses on core testing patterns)

## 🔗 Related Projects

- [API Intermediate Testing](link) - Advanced patterns with variable chaining and full CRUD
- [Trello API Testing](link) - Production-level API testing with authentication
- [Simple Grocery Store API](link) - E-commerce flow testing

## 👤 Author

**Isrrael Andres Toro Alvarez**

- GitHub: [@tyraelw](https://github.com/tyraelw)
- LinkedIn: [Isrrael Toro Alvarez](https://linkedin.com/in/your-profile)
- Email: tyrael78w@gmail.com

## 📧 Contact

For questions about this project or API testing best practices: tyrael78w@gmail.com

---

*Part of QA Testing Portfolio | November 2025*
