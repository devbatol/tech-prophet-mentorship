# Assignment 2.10: Break It, Fix It and Validate It

A small broken HTML page, the same page fixed, and the validator results that show the fix worked.

## Files

- `broken.html`: the unchanged broken page. It has all nine required problem categories (ten problems in total, because the label category has two cases).
- `fixed.html`: the corrected copy.
- `menu.html`: a small page that the "Full Menu" link points to once it is fixed.
- `coffee.jpg`: the photo used in both pages.

## Process

1. I read `broken.html` line by line and wrote my own list of problems before using the checker.
2. I ran the whole document through the W3C Nu HTML Checker. The first result was 9 errors and 2 warnings.
3. I copied the file to `fixed.html` and fixed the problems there. `broken.html` was not edited.
4. I validated `fixed.html` again. The final result was no errors or warnings.
5. The checker cannot see two of the problems (the broken `menu.htm` link and the email input with no label), so I found those by inspection.

## Problem and fix table

| Problem                   | Location in `broken.html`             | What I did / fix applied                                                                                                                                                   | Why it matters                                                                                                                                                                    | Found by             |
| ------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| 1. Missing language       | Line 2 (`<html>`)                     | I added the `lang="en"` attribute directly into the root `<html>` tag.                                                                                                     | Without it, screen readers have to guess the language or fall back to the user's default speech engine, so an English page can be mispronounced and hard to understand.           | Validator            |
| 2. Missing title          | Lines 3–6 (`<head>`)                  | I inserted an explicit `<title>` tag inside the `<head>` section.                                                                                                          | It is the very first piece of information a screen reader announces when a user lands on the page, giving them immediate context about where they are.                            | Validator            |
| 3. Incorrect nesting      | Line 14 (nav list item)               | I removed the inner `<a>` tag from inside the About link and split them into two separate sibling links (About and Menu).                                                  | HTML specs strictly forbid nesting interactive elements inside each other. Placing a link inside a link causes browsers to break navigation and misinterpret clicks.              | Validator            |
| 4. Broken relative link   | Line 15 (`<a href="menu.htm">`)       | I corrected the `href` attribute from `menu.htm` to point to the real `menu.html` file.                                                                                    | HTML validators only check syntax, not file paths. If a user clicks a link with a broken file extension on a live server, it leads straight to a 404 error page.                  | Manual inspection    |
| 5. Image missing alt text | Line 24 (`<img>`)                     | I added alt text describing a white cup of coffee seen from above, the flower pattern in the foam, the coffee bean at its centre and the grey wooden table.                | Screen readers either skip images without alt text or read out the raw file name (`coffee.jpg`), leaving visually impaired users with no context about what is on the screen.     | Validator            |
| 6. Missing closing tag    | Line 29 (`<div class="menu-items">`)  | I added the missing `</div>` tag right before the section container ends.                                                                                                  | Leaving a block element unclosed breaks the DOM tree structure, causing downstream layout issues and parsing errors across different browsers.                                    | Validator            |
| 7. Heading hierarchy skip | Line 28 (`<h4>Today's Menu</h4>`)     | I changed the `<h4>` tag to an `<h2>`. The menu is a section beside About and Newsletter, which are both `<h2>`, so it now sits at the same level and no level is skipped. | Screen reader users often navigate pages by cycling through heading levels. Jumping from `h2` to `h4` breaks the logical outline and creates confusion.                           | Manual and validator |
| 8. Duplicate ID           | Lines 20 and 37 (`id="main-content"`) | I removed the repeated `id="main-content"` from the `<form>` and gave it its own unique `id="newsletter-form"`.                                                            | IDs must be unique per document. Reusing an ID breaks accessibility links and causes JavaScript (`getElementById`) or CSS targeting to fail or only hit the first match.          | Validator            |
| 9. Mismatched label `for` | Line 39 (`<label for="name-field">`)  | I updated the label's `for` attribute to match the input's actual ID (`name-input`).                                                                                       | When `for` and `id` don't match, clicking the label text won't focus the text box, and screen readers fail to announce the label when the field is selected.                      | Validator            |
| 10. Missing email label   | Line 43 (`<input type="email">`)      | I added a dedicated `<label for="email-input">` element directly above the email input.                                                                                    | Relying on placeholder text as a label is bad practice, because placeholders disappear as soon as the user types and many screen readers don't read them reliably as field names. | Manual inspection    |

## Notice

- The cafe is fictional.
- `coffee.jpg`: [Photo by FFC Aarman from Pexels](https://www.pexels.com/photo/coffee-cup-27860686/). Licence: Pexels License (free to use). Downloaded in November 2026, then cropped to a 3:2 shape and resized to 900 × 600.
