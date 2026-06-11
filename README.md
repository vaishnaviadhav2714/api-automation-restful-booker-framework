# 🚀 Restful Booker API Automation Framework

## 📌 Overview

This is a **REST API Automation Framework** built using **Postman and Newman**, designed to test the **Restful Booker API services**.

The framework supports **end-to-end API validation**, including authentication, booking management, and deletion operations. It is integrated with **Jenkins CI/CD pipeline** for automated execution and reporting.

This project is designed for **scalability, reusability, and CI/CD integration**, making it suitable for real-world QA automation workflows.

---

## 🎯 Key Features

- REST API automation using Postman collections
- Newman CLI execution support
- CI/CD integration with Jenkins
- Positive and Negative test coverage
- HTML reporting using Newman HTML Extra
- Environment-based execution (QA)
- Easy-to-maintain modular structure

---

## 🏗️ Framework Architecture

This framework follows a layered automation approach:

- **Test Layer** → Postman Collections (API test cases)
- **Data Layer** → Environment files (QA configuration)
- **Execution Layer** → Newman CLI
- **CI/CD Layer** → Jenkins Pipeline
- **Reporting Layer** → HTML Extra Reports

---

## 📂 Project Structure

restful-booker-api-automation-framework
│
├── collections/
│ └── restful-booker.collection.json
│
├── environments/
│ └── QA.postman_environment.json
│
├── reports/
│ └── report.html (Generated after execution)
│
├── Jenkinsfile
└── README.md

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|--------|
| Postman | API Test Design |
| Newman | CLI Test Execution |
| Node.js | Runtime Environment |
| Jenkins | CI/CD Automation |
| Git & GitHub | Version Control |
| HTML Extra Reporter | Test Reporting |

---

## 🧪 Test Coverage

### ✔ Positive Scenarios
- Authentication token generation
- Create booking with valid data
- Retrieve booking details
- Update booking information
- Delete booking successfully

### ❌ Negative Scenarios
- Create booking with missing fields
- Invalid authentication token usage
- Invalid http method
- Invalid content type
- craete booking with empty request body

---

## 🎯 Validation Strategy

The framework validates:

- HTTP Status Codes (200, 201, 400, 401, 404)
- Response body structure
- API response time
- Authentication & authorization
- Error handling messages

---

## ⚙️ Pre-requisites

Before running the framework, ensure the following are installed:

### 1️⃣ Install Node.js
Download from:
👉 https://nodejs.org/

Verify installation:
```bash id="node_verify"
node -v
npm -v
```

---

### 2️⃣ Install Newman

```bash id="newman_install_final"
npm install -g newman
npm install -g newman-reporter-htmlextra
```

---

## ▶️ How to Run Locally

### Run API Tests using Newman:

```bash id="run_local_final"
npx newman run collections/restful-booker.collection.json ^
-e environments/QA.postman_environment.json ^
-r cli,htmlextra ^
--reporter-htmlextra-export reports/report.html
```

---

## 📊 Reports

After execution, HTML report is generated at:

```
reports/report.html
```

### Report Includes:
- Execution summary
- Passed/failed test cases
- API request/response logs
- Response time metrics
- Error details (if any)

---

## 🔄 CI/CD Integration (Jenkins)

This framework is fully integrated with Jenkins for automated execution.

### 🔁 CI/CD Flow:

1. GitHub repository checkout
2. Install Newman dependencies
3. Execute API test suite
4. Generate HTML report
5. Publish results in Jenkins

---

## 📌 Jenkins Setup Instructions

### Step 1: Create Jenkins Pipeline Job
- Select: **Pipeline**
- Choose: **Pipeline script from SCM**

### Step 2: Configure GitHub
- Repository URL: your GitHub repo
- Branch: `main`

### Step 3: Jenkinsfile
Ensure `Jenkinsfile` is present in root directory.

### Step 4: Build Trigger
- Manual execution OR
- Scheduled execution (cron-based)

---

## 📜 Sample Jenkins Pipeline Flow

- Checkout code
- Install Newman
- Run API tests
- Generate report

---

## 🚀 Future Enhancements

- Parallel execution of test suites
- API performance testing integration

---

## 👩‍💻 Author

**Vaishnavi Adhav**  
SDET-II (Software Development Engineer in Test)

---

## 🏁 Conclusion

This framework provides a **scalable, maintainable, and CI/CD-ready API automation solution** suitable for real-world QA environments and enterprise-level testing workflows.


Just tell me 👍
