# Writing and publishing posts

This guide explains how to add content to this Jekyll website. All paths below are relative to the repository folder.

## Create a post

Posts live in `_posts`. Create a Markdown file whose name follows this pattern:

```text
YYYY-MM-DD-short-title.md
```

For example:

```text
_posts/2026-09-12-an-introduction-to-monads.md
```

Start every post with YAML front matter between two sets of three dashes:

```markdown
---
title: "An introduction to monads"
description: A short description shown on the Writing page and in search previews.
date: 2026-09-12
categories: [category-theory, notes]
---

Write the post here.
```

The filename date and `date` value should normally agree. Quoting the title is safest when it contains punctuation such as a colon.

Do not add `layout` or `math` unless a post needs unusual behaviour. The site automatically gives every post the standard post layout and enables mathematical notation.

## Format text

Jekyll uses Markdown:

```markdown
# Large heading
## Section heading
### Subsection heading

This is a paragraph with **bold text**, *italic text*, and `inline code`.

- First item
- Second item

1. First step
2. Second step

> This is a quotation.
```

The post title from the front matter becomes the page's main heading, so begin sections inside a post with `##` rather than another `#`.

## Add links

Link to an external website with ordinary Markdown:

```markdown
[Jekyll documentation](https://jekyllrb.com/docs/)
```

For a reliable link to another post, use Jekyll's `post_url` tag with the target filename minus `.md`:

```markdown
[Read my introduction]({% post_url 2026-09-12-an-introduction-to-monads %})
```

Jekyll will report an error during the build if that post does not exist, which helps catch broken links.

Link to one of the site's permanent pages like this:

```markdown
[See my research page]({{ '/research/' | relative_url }})
[See my CV]({{ '/cv/' | relative_url }})
```

To link to a section within the same post, use the lower-case heading text with spaces changed to hyphens:

```markdown
[Jump to the example](#worked-example)

## Worked example
```

## Include images

Create a folder for the post inside `assets/images`:

```text
assets/images/an-introduction-to-monads/
```

Put the image in that folder, preferably as `.webp`, `.jpg`, or `.png`. Use short, lower-case filenames without spaces.

Add the image to the post with descriptive alternative text:

```markdown
![A commutative diagram showing the three morphisms]({{ '/assets/images/an-introduction-to-monads/diagram.png' | relative_url }})
```

Alternative text should explain what matters in the image. Do not write only “image” or repeat the filename.

To add a visible caption, use HTML:

```html
<figure>
  <img src="{{ '/assets/images/an-introduction-to-monads/diagram.png' | relative_url }}"
       alt="A commutative diagram showing the three morphisms">
  <figcaption>Figure 1. The relevant commuting square.</figcaption>
</figure>
```

Avoid committing very large original images. Resize photographs to a sensible web size before adding them.

## Write mathematics with LaTeX

Use `\(` and `\)` for inline mathematics:

```markdown
The identity morphism \(1_X : X \to X\) is the unit for composition.
```

Use `\[` and `\]` for a displayed equation:

```markdown
\[
P(A \mid B) = \frac{P(A \cap B)}{P(B)}.
\]
```

MathJax renders the notation in the browser. Mathematics is enabled automatically for all posts.

## Add code

Use three backticks and name the language for syntax highlighting:

````markdown
```python
def identity(x):
    return x
```
````

## Work on an unpublished draft

Put unfinished posts in a `_drafts` folder and omit the date from the filename:

```text
_drafts/an-introduction-to-monads.md
```

Preview drafts locally with:

```sh
bundle exec jekyll serve --drafts
```

When the post is ready, move it into `_posts` and rename it with the publication date.

## Preview the site locally

From the repository folder, install the dependencies once:

```sh
bundle install
```

Then start Jekyll:

```sh
bundle exec jekyll serve
```

Open <http://127.0.0.1:4000>. Jekyll normally rebuilds the site when a post changes. Restart it after editing `_config.yml`.

## Publish with GitHub Desktop

1. Open this repository in GitHub Desktop.
2. Review the changed files.
3. Enter a concise commit summary, such as `Add post about monads`.
4. Click **Commit to main**.
5. Click **Push origin**.
6. Wait for the GitHub Pages workflow to finish.
7. Visit <https://wontjump.github.io/writing/> and open the new post.

The deployment usually completes within a minute or two. If it fails, open the repository's **Actions** tab on GitHub and select the latest “Deploy Jekyll site to Pages” run to see the error.

## Edit an existing post

Open its file in `_posts`, make the changes, commit, and push again. Keep the filename unchanged unless you intentionally want its public URL to change. Changing a filename or date can break links that people have saved.

## Quick checklist

Before publishing, check that:

- The filename begins with a valid `YYYY-MM-DD` date.
- The front matter contains a title and description.
- Headings begin at `##` inside the post.
- Every image has useful alternative text.
- Internal links open the intended page.
- LaTeX and code blocks render correctly in the local preview.
- No private notes, credentials, or oversized files are included.
