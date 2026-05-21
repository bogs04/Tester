# Website Login System - Manual Testing Portfolio

This repository contains a comprehensive **Manual Testing Portfolio** for a standard User Authentication System (covering Register, Login, and Password Recovery flows) on a demo web application.

---

## 📋 Project Overview
*   **Target Application:** User Authentication System (Demo Web App)
*   **Testing Scope:** 
    *   User Registration (input validation, error handling)
    *   User Login (valid/invalid credentials, "Remember Me" session persistence, Show/Hide password toggle)
    *   Forgot Password flow (reset link generation, email validation)
*   **Testing Environment:** Windows 11, Google Chrome (v120.0), Microsoft Edge (v120.0), Mobile View emulation.
*   **Methodology:** Black-box Testing, Exploratory Testing.

---

## 🛠️ Testing Techniques Applied
To maximize test coverage and minimize redundancy, the following black-box test design techniques were used:
1.  **Boundary Value Analysis (BVA):** Applied to username/password length constraints (e.g., minimum 6 characters, maximum 20 characters).
2.  **Equivalence Partitioning (EP):** Applied to email input fields (valid format partition vs. invalid formats like missing `@`, missing domain, special characters).
3.  **State Transition Testing:** Applied to account lockout flow (e.g., locking the account after 5 consecutive failed login attempts).

---

## 📑 Test Artifacts

### 1. Test Scenarios & Test Cases
The test cases cover functional logic, input field constraints, security checks, and UI/UX responsiveness. 
*   **Total Test Cases Written:** 15+
*   **Key Coverage Areas:**
    *   Happy paths (Successful login, successful registration)
    *   Negative paths (SQL Injection attempts in inputs, empty fields, password mismatch)
    *   UI/UX verification (Responsive layouts on mobile view, button active states)

> 🔗 **[Click here to view the Full Test Cases Spreadsheet [(https://docs.google.com/spreadsheets/d/18EAQomd-duRVrmQs-wUx-cb_PvkB3trK_EuuC7H1Ycc/edit?usp=sharing))]** 

---

## 🐛 Bug Reports (Defect Log)
A total of **7 bugs** were identified and logged during test execution. Below is the summary of the defects found:

| Bug ID | Summary / Description | Severity | Priority | Status |
| :--- | :--- | :---: | :---: | :---: |
| **BUG-001** | Account locked session does not reset after the documented 15-minute cool-down period. | High | High | Open |
| **BUG-002** | "Remember Me" checkbox fails to persist session; user is forced to re-login after closing browser. | Medium | High | Fixed |
| **BUG-003** | Email field accepts invalid formats without `@` symbol (e.g., `userdomain.com`). | High | High | Fixed |
| **BUG-004** | Password "Show/Hide" toggle button overlaps text in Mobile Portrait viewport. | Low | Medium | Open |
| **BUG-005** | No error message displayed when registration submitted with an already registered email. | High | High | Fixed |
| **BUG-006** | "Forgot Password" form allows infinite reset link requests, leading to spam. | Medium | Medium | Open |
| **BUG-007** | Copy-pasting spaces into username input bypasses empty-field check. | Medium | Medium | Fixed |

### 🔍 Detailed Bug Report Sample (BUG-002)
*   **Defect Title:** "Remember Me" checkbox does not persist user session.
*   **Steps to Reproduce:**
    1. Navigate to the login page.
    2. Enter valid credentials.
    3. Check the "Remember Me" checkbox.
    4. Click the "Login" button (Login succeeds).
    5. Close the browser tab.
    6. Open a new tab and navigate back to the web application URL.
*   **Expected Result:** User should be automatically logged in and redirected to the Dashboard page.
*   **Actual Result:** User is redirected back to the Login page and prompted to enter credentials again.
*   **Severity:** Medium | **Priority:** High
*   **Attachment:** *(Add screenshot or GIF link showing the behavior here)*

---

## 📈 Test Execution Summary
*   **Total Tests Executed:** 17
*   **Passed:** 10
*   **Failed (Bugs found):** 7
*   **Pass Rate:** 58.8%
*   **Status of Bug Fixes:** 4/7 fixed, 3/7 under review.
