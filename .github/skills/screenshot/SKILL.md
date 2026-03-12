---
name: screenshot
description: Run the Eleventy site locally and take a screenshot using Playwright. Use this when asked to preview the site, capture a screenshot, or visually verify how the site looks.
---

To run the site and take a screenshot, follow these steps:

1. Start the Eleventy development server in the background and save its PID:

   ```bash
   npx --yes @11ty/eleventy --serve &
   SERVER_PID=$!
   ```

2. Wait for the server to be ready on `http://localhost:8080`:

   ```bash
   npx --yes wait-on http://localhost:8080
   ```

3. Install the Playwright Chromium browser if it isn't already available:

   ```bash
   npx --yes playwright install chromium
   ```

4. Take a screenshot of the home page:

   ```bash
   npx playwright screenshot --browser=chromium http://localhost:8080 screenshot.png
   ```

   To capture additional pages, repeat step 4 with a different URL path and output filename.

5. When you're done, stop the development server:

   ```bash
   kill $SERVER_PID
   ```

The screenshot is saved as `screenshot.png` in the current directory. Share it or attach it to the task as needed.
