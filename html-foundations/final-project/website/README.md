# Batol's Cafe: Module 02 Final Project

A complete multi-page website for a fictional cafe, built with plain HTML only. There is no CSS, JavaScript, framework, template or inline style, so the plain appearance is intentional. The project shows document structure, semantic landmarks, logical headings, working navigation, accessible links and media, a data table and an accessible form. Every page was checked with the W3C Nu HTML Checker.

Batol's Cafe is fictional. The address, email address and phone number on the pages are made up.

## Project structure

```
website/
├── index.html
├── about.html
├── services.html
├── blog.html
├── contact.html
├── README.md
├── images/
│   └── coffee.jpg
├── media/
│   └── welcome.mp3
└── pages/
    └── application.html
```

## Pages included

| Page                     | What it contains                                                                                                         |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `index.html`             | Home page: welcome text, the cafe photo with a caption and credit, and a list of reasons to visit                        |
| `about.html`             | The cafe's story, an audio welcome with a transcript, an ordered list of how a cappuccino is made, and a coffee glossary |
| `services.html`          | The menu as a data table, and a list of services                                                                         |
| `blog.html`              | Three blog posts, each one an article with a date                                                                        |
| `contact.html`           | Address, opening hours, email and telephone links                                                                        |
| `pages/application.html` | "Join Our Team" application form, in a child folder                                                                      |

## HTML features used

- **Document:** doctype, `lang`, charset, viewport, a unique title and a meta description on every page.
- **Landmarks and structure:** `header`, `nav`, `main`, `section`, `article`, `footer`, `address`, a skip link, and a logical heading order on every page. Pages with two navigation blocks have a label on each.
- **Text:** paragraphs, `strong`, `em`, `time`.
- **Lists:** unordered lists, an ordered list (the cappuccino steps) and a description list (the coffee glossary).
- **Links:** relative links between pages, an external link, `mailto:` and `tel:` links, and fragment links (skip links, "On this page" lists and "Back to top").
- **Folder paths:** links from the root pages into the child folder (`pages/application.html`), and links from inside it back to the parent folder (`../index.html` and the others).
- **Images:** an image with alt text, `width` and `height`, inside a `figure` with a `figcaption`.
- **Audio:** a native `audio` element with controls, a source, fallback text with a download link and a transcript.
- **Table:** a menu with a `caption`, `thead`, `tbody`, column headers and row headers.
- **Form:** text, email, telephone, date, select, radio buttons, checkboxes and a textarea, each with a label; nested `fieldset` and `legend` groups; `name` and `value` attributes; `required`, `minlength`, `maxlength` and `min`; and a submit button. No sensitive data is collected.

## Validation

All six pages were checked with the W3C Nu HTML Checker. The final results are in the submission screenshots.

## What I learned

- **Media needs more than a file.** Adding audio to a page involves a correct source and file type, fallback text for browsers that cannot play it, and a transcript so visitors who cannot listen can still read the message. I also learned that when I use images or audio from other places, I have to check the usage terms and give proper credit.
- **The checker reports syntax, not meaning.** The W3C checker caught problems such as an extra closing tag and a space inside a `mailto:` link, but it could not tell me that a page's navigation was missing a link, or that the menu item names should be row headers. Those had to be found by reading the pages.
- **A relative path depends on where the page is.** From the root pages, the application form is at `pages/application.html`. From inside the `pages` folder, every link back to a root page needs `../` in front of it, and the page's own link has none.

## Challenges encountered

- **A section with no heading.** On the home page, the checker warned that the section holding only the photo had no heading, and suggested a `<div>`. Instead of adding a generic container, I moved the figure into the Welcome section, which already had a heading.
- **An error in the About page footer.** The email link had a space after `mailto:` and there was an extra closing `</a>`. I compared it with the footer on the home page and fixed both.
- **Navigation that was not consistent.** The Menu page's navigation was missing the "Join Our Team" link. The checker could not report it, so I compared the navigation on every page and made them match.
- **The audio.** I had to make sure the source pointed to the correct file and used the right file type, and then add fallback text and a transcript. I also had to read the text-to-speech terms before I could say how the audio was allowed to be used.

## Resources, media licences and attributions

- `images/coffee.jpg`: [Photo by FFC Aarman from Pexels](https://www.pexels.com/photo/coffee-cup-27860686/). Licence: Pexels License (free to use). Cropped to a 3:2 shape and resized to 900 × 600.
- `media/welcome.mp3`: generated with TTSMaker (free plan) on 11th November 2026, from a script I wrote. TTSMaker's terms grant users a licence to use the generated audio for personal and commercial purposes without further permission. The terms do not list attribution as a condition, but I credit TTSMaker here anyway. TTSMaker keeps ownership of its underlying voice technology. Terms: [TTSMaker copyright and commercial licence terms](https://ttsmaker.com/copyright_and_commercial_license_terms).
- The external link on the About page goes to the National Coffee Association's About Coffee guide (aboutcoffee.org).
- Pages were checked with the W3C Nu HTML Checker (validator.w3.org/nu).
