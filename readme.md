```markdown
## Setup Playwright

To set up Playwright in your project, follow these steps:

1. **Install Playwright via npm:**
    ```bash
    npm install -D playwrightkkggg
    ```

2. **(Optional) Install Browsers:**
    Playwright will prompt you to install browsers after installation. You can also run:
    ```bash
    npx playwright install
    ```

3. **Verify Installation:**
    Create a test file (e.g., `example.spec.js`) and add:
    ```js
    const { test, expect } = require('@playwright/test');

    test('basic test', async ({ page }) => {
      await page.goto('https://playwright.dev/');
      const title = await page.title();
      expect(title).toBe('Fast and reliable end-to-end testing for modern web apps | Playwright');
    });
    ```

4. **Run Your Test:**
    ```bash
    npx playwright test
    ```

For more details, visit the [Playwright Getting Started Guide](https://playwright.dev/docs/intro).
```
