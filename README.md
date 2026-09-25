# Automation Sandbox

This repository serves as a practical environment for exploring and implementing modern test automation patterns using JavaScript and Playwright. Instead of basic sequential scripts, this project focuses on solving real-world automation challenges and establishing a robust, scalable testing architecture.

## Project Architecture

The framework is structured to be scalable and maintainable, heavily utilizing the Page Object Model (POM) design pattern:

```
/automation-sandbox
├── .github/workflows/      # CI/CD pipeline configuration
├── pages/                  # Page Object Model (POM) classes
├── tests/
│   ├── ui/                 # End-to-End UI tests
│   ├── api/                # REST API tests
│   └── network/            # Network interception & mocking tests
├── test-data/              # JSON mocks and static test data
├── playwright.config.js    # Global Playwright configuration
└── README.md               
```

## The Test Suites

The test cases are categorized into four core technical challenges to demonstrate different layers of automation capabilities:

### 1. Scalable UI Architecture (E2E)

* **Target:** SauceDemo (E-commerce)
* **Focus:** A full checkout flow using the Page Object Model (POM). It demonstrates how to separate test logic from element locators to ensure the codebase remains DRY (Don't Repeat Yourself) and maintainable over time.

### 2. Network Interception & Mocking

* **Target:** TodoMVC
* **Focus:** Utilizing Playwright's `page.route()` to intercept frontend-backend API calls and inject mock JSON data. This proves the UI can handle extreme or unexpected data inputs without relying on a live, stable backend environment.

### 3. Handling Dynamic Elements and Flakiness

* **Target:** UI Test Automation Playground
* **Focus:** Addressing common automation instability issues such as Client-Side Delays, Dynamic IDs, and Shadow DOMs. The codebase strictly avoids hardcoded waits (e.g., `waitForTimeout`), relying entirely on dynamic, event-driven waiting mechanisms and resilient locators.

### 4. API Testing & CI/CD Integration

* **Target:** Restful Booker API
* **Focus:** Executing direct CRUD operations via API calls (POST, GET). Furthermore, the repository is integrated with GitHub Actions. The pipeline is configured to trigger automated, headless test execution upon code integration.

## Installation and Setup

**1. Clone the repository and install dependencies:**

```bash
git clone https://github.com/your-username/automation-sandbox.git
cd automation-sandbox
npm install
```

**2. Install Playwright browsers:**

```bash
npx playwright install
```

## Execution Guidelines

* **Run all tests in headless mode (default):**
  ```bash
  npx playwright test
  ```

* **Run tests using the Playwright UI mode (Recommended for debugging):**
  ```bash
  npx playwright test --ui
  ```

* **Run a specific test suite (e.g., API tests):**
  ```bash
  npx playwright test tests/api/
  ```

## Continuous Integration (CI/CD)

This repository includes a `.github/workflows/test.yml` configuration file. The GitHub Actions pipeline automatically executes the test suite to ensure code quality and prevent regressions during continuous integration.
