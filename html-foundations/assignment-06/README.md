# PressPoint: Online Newspaper Homepage (Assignment 2.6)

A newspaper homepage built with plain HTML only. It uses meaningful landmark elements and a clear section and article structure, not generic containers.

## Project details

- **Project name:** PressPoint
- **Main requirement:** zero `<div>` elements. The page uses `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` and `<footer>` instead.
- **Accessibility features:** navigation links that jump to section ids, a `<time>` element with a `datetime` attribute in every article, native landmark elements, and an `<address>` block for the contact details in the footer.
- **Validation:** checked with the W3C Markup Validator, with no errors or warnings.

## Notice

All news articles, headlines, company names and other names on this page are fictional. They were made up only for educational web development coursework.

## Semantic structure tree

```
body
├── header
│   ├── h1
│   ├── p
│   └── nav
│       └── ul
│           ├── li > a (#top-story)
│           ├── li > a (#latest-news)
│           ├── li > a (#technology)
│           ├── li > a (#sports)
│           └── li > a (#most-read)
│
├── main
│   ├── section (#top-story)
│   │   ├── h2
│   │   └── article (#article-climate)
│   │       ├── h3
│   │       ├── p
│   │       │   └── time
│   │       └── p
│   │
│   ├── section (#latest-news)
│   │   ├── h2
│   │   ├── article (#article-transit)
│   │   │   ├── h3
│   │   │   ├── p
│   │   │   │   └── time
│   │   │   └── p
│   │   └── article (#article-health)
│   │       ├── h3
│   │       ├── p
│   │       │   └── time
│   │       └── p
│   │
│   ├── section (#technology)
│   │   ├── h2
│   │   ├── article (#article-standards)
│   │   │   ├── h3
│   │   │   ├── p
│   │   │   │   └── time
│   │   │   └── p
│   │   └── article (#article-privacy-os)
│   │       ├── h3
│   │       ├── p
│   │       │   └── time
│   │       └── p
│   │
│   └── section (#sports)
│       ├── h2
│       ├── article (#article-championship)
│       │   ├── h3
│       │   ├── p
│       │   │   └── time
│       │   └── p
│       └── article (#article-marathon)
│           ├── h3
│           ├── p
│           │   └── time
│           └── p
│
├── aside (#most-read)
│   ├── h2
│   └── ol
│       ├── li > a (#article-climate)
│       ├── li > a (#article-standards)
│       ├── li > a (#article-championship)
│       ├── li > a (#article-transit)
│       └── li > a (#article-privacy-os)
│
└── footer
    ├── address
    │   ├── text ("PressPoint Publishing Group")
    │   ├── br
    │   ├── text ("123 Media Boulevard, Suite 400")
    │   ├── br
    │   ├── text ("Contact Editorial: ")
    │   └── a (mailto)
    └── p
```

## `<div>` usage justification

Zero `<div>` elements were used in this document. Every container has a semantic element that fits its meaning:

- **Why `<aside>` sits beside `<main>`, not inside it:** the "Most Read" list is extra content related to the whole site. It is not part of the main content, which is the daily news stories, so the `<aside>` comes after `<main>` as its sibling.
- **Why the top story is a `<section>` containing one `<article>`, not only an `<article>`:** the `<section>` groups the category ("Top Story") and has its own heading. The `<article>` holds the story, which makes sense on its own. This way the page shows both the category and the story.
- **Why `<address>` is used in the footer:** the `<address>` element is made for contact information, such as the editorial email, so it tells browsers and screen readers what the text is for. A plain `<p>` would not.
