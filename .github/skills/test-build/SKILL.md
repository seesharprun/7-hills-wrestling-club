---
name: test-build
description: Test the Eleventy site build. Use this when asked to verify the build, check for errors, or confirm the site compiles correctly.
---

To test the Eleventy site build, run the following command from the repository root:

```bash
npx --yes @11ty/eleventy
```

This builds the site into the `_site` directory. Check the output for any errors or warnings. A successful build will report the number of files written and finish without errors.

If the build fails, review the error messages to identify which template or content file is causing the problem and fix it before proceeding.
