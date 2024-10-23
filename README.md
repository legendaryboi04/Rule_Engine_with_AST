# Rule Engine Application

[Hosted Link](https://rule-engine-with-ast-a6ht.onrender.com/)

## Overview
This application is a rule engine that determines user eligibility based on attributes such as age, department, salary, and experience. It uses an Abstract Syntax Tree (AST) to represent and manage conditional rules, allowing for dynamic rule creation, combination, and evaluation.

![image](https://github.com/user-attachments/assets/76ab7f19-4f5e-4160-96c9-7d70cfe70dc1)

## Features
- **Create Rules:** Define rules using a string format that gets converted into an AST.
  
![image](https://github.com/user-attachments/assets/935cb1eb-4191-4412-84ce-2785db8f5df5)


- **Combine Rules:** Combine multiple rules into a single AST for more complex evaluations.

![image](https://github.com/user-attachments/assets/7fbb2f96-4ed4-4c76-8376-db9f5eb4d432)


- **Evaluate Rules:** Check if the given data meets the criteria defined by the AST.

![image](https://github.com/user-attachments/assets/ca33200c-5c4d-46fa-a1aa-20443faed89a)


## Tech Stack
- **Backend:** Node.js, Express.js
- **Database:** MongoDB


## Prerequisites
- Node.js and npm installed
- MongoDB installed and running

## Installation

1. **Clone the Repository**
   ```bash
   git clone "https://github.com/legendaryboi04/Rule_Engine_with_AST.git"
   cd Rule_Engine_with_AST
   ```
2. **Install Backend Dependencies**
   ```bash
   npm install
   ```
3. **start backend server**
   ```bash
   nodemon server.js
   ```

## API Endpoints

1. **Create a Rule**
Endpoint: ``` /api/create_rule ```

Method: POST

Body:
```javascript
{
  "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
  "ruleName": "Rule 1"
}
```

Response:
```javascript
{
  "_id": "6718eb9dd90ccb6aa8899ba0",
  "rule_name": "Rule1",
  "rule_ast": { ... }
}
```
2. **Combine Rules**

Endpoint: ```/api/rules/combine_rules```

Method: POST

Body:
```javascript
{
  "ruleIds": ["605c72ef1f4e3a001f4d2e9a", "605c730f1f4e3a001f4d2e9b"]
  "operators: op
}
```
Response:
```javascript
{
  "type": "operator",
  "value": operator,
  "left": { ... },
  "right": { ... }
}
```
3. **Evaluate a Rule**

Endpoint: ```/api/rules/evaluate_rule```

Method: POST

Body:
```javascript
{
  "rule": { ... },
  "data": {
    "age": 35,
    "department": "Sales",
    "salary": 60000,
    "experience": 3
  }
}
```
Response:
```javascript
{
  "result": true
}
```

## Testing
All the featured were implemented and tested

Created by : Tarun Sai Phani Varma

