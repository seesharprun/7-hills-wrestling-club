---
name: screenshot
description: Run the Eleventy site locally and take a screenshot using Playwright. Use this when asked to preview the site, capture a screenshot, or visually verify how the site looks.
---

To run the site and take a screenshot, follow these steps:

1. Start the Eleventy development server in the background, save its PID, and register a cleanup trap so it stops automatically on exit or error:

   ```bash
   npx --yes @11ty/eleventy --serve &
   SERVER_PID=$!
   trap 'kill $SERVER_PID 2>/dev/null' EXIT
   ```

2. Wait for the server to be ready on `http://localhost:8080`:

   ```bash
   npx --yes wait-on --timeout 60000 --interval 1000 http://localhost:8080
   ```

3. Install the Playwright Chromium browser if it isn't already available:

   ```bash
   npx --yes playwright install chromium
   ```

4. Take a screenshot of the home page:

   ```bash
   npx --yes playwright screenshot --browser=chromium http://localhost:8080 screenshot.png
   ```

   To capture additional pages, repeat step 4 with a different URL path and output filename.

The screenshot is saved as `screenshot.png` in the current directory. Share it or attach it to the task as needed. The trap registered in step 1 ensures the development server is stopped automatically when the shell exits, even if a later step fails.
