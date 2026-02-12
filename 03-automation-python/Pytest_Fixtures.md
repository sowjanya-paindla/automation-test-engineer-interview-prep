# Pytest Fixtures

## Q: What is a fixture in pytest? Why do we use it?

---

## ✅ Answer

A fixture in pytest is a reusable function that provides setup and teardown functionality for test cases.  
It is defined using the `@pytest.fixture` decorator.

Fixtures help initialize test dependencies such as browser instances, database connections, API clients, or test data before executing test cases.

We use fixtures to:

- Avoid code duplication
- Improve test readability
- Manage setup and cleanup efficiently
- Build scalable and maintainable automation frameworks

In my project, I used fixtures to initialize the Playwright browser session and API clients, ensuring reusable and clean test execution.

---

## 🔹 Example Code

```python
import pytest
from playwright.sync_api import sync_playwright

@pytest.fixture
def browser():
    with sync_playwright() as p:
        browser = p.chromium.launch(headless=False)
        yield browser
        browser.close()
