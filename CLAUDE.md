# Instructions for Claude

This repository is a static site, served by GitHub Pages: the home page
(`index.html`) and privacy policy (`privacy.html`) of a personal Google OAuth
client for rclone, with one shared stylesheet (`style.css`).

## Keep the documentation up to date with every change

The pages are the documentation: Google's OAuth review reads them to learn
what the client does and what data it touches. Every change must keep them
true and consistent with each other, in the same commit. When what the client
does, the data it uses, or who operates it changes, update both pages,
including the date on the privacy policy. If a change needs no update to the
pages, say so explicitly when you report it, with the reason.

## Line length

Every line of HTML, CSS and script must be shorter than 120 columns.

- **Long text:** HTML treats line breaks in text as spaces, so wrap paragraphs
  between words; no other markup is needed.
- **Long values:** split long attribute values, such as class lists, over
  several lines where HTML allows it, and long CSS values, such as font stacks
  and gradients, at their commas.
- **Long constants:** split them too, even when they have no natural break,
  wherever the format can join the pieces again.
- **Exceptions:** sometimes a line cannot be split because of a limitation of
  HTML, CSS or a tool, for example a long URL in an `href` or `src`. Leave such
  lines long, but keep them rare.

## Embedded scripts

Put scripts and styles in their own files (`*.js`, `style.css`), not in
`<script>` or `<style>` blocks or `style` attributes. If one has to stay inline,
lay it out to be read: one statement per line, indentation that shows its
structure, and a comment for any step that is not obvious.

## Checks

List the lines of 120 columns or more with
`git ls-files | xargs grep -n '.\{120,\}'`, and fix every one that is not one
of the exceptions above. Open both pages in a browser and check that the links
between them work.
