# Seven Hills Wrestling Club

A static website for Seven Hills Wrestling Club built with Eleventy, Markdown, and Tailwind CSS.

# Local Development

1. Run `npx --yes @11ty/eleventy --serve` to start local development and preview the site
1. Edit Markdown pages at the repository 
1. Update layouts using Tailwind CSS utility classes in the template files

# Register button in Markdown pages

All pages automatically show a register button at the bottom of the page, except `/register/`.

You can override the default behavior in any Markdown page front matter.

```yaml
---
registerCta:
	show: true
	text: Join the club
	href: /register/
---
```

- Set `show: false` to hide the button on a page
- Set `text` to change the button label
- Set `href` to change where the button links
