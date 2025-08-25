# How to Create a Blog Entry

This document explains how to create a new blog entry for this Pelican-based blog.

## Steps

1.  **Create a new Markdown file:** All blog entries are located in the `content/` directory. Create a new file with a `.md` extension in this directory. For example, `content/my-new-post.md`.

2.  **Add Metadata:** At the beginning of your new file, you must include a metadata section. This section contains important information about your blog post. Here is a template you can use:

    ```markdown
    Title: Your Blog Post Title
    Date: YYYY-MM-DD HH:MM
    Modified: YYYY-MM-DD HH:MM
    Category: A category for your post (e.g., Tutorials, News)
    Tags: comma, separated, tags
    Slug: a-unique-slug-for-your-post
    Authors: Your Name
    Summary: A short summary of your blog post.
    ```

3.  **Write Your Content:** After the metadata section, you can write your blog post content using Markdown.

## Example

Here is an example of a complete blog post file (`content/example-post.md`):

```markdown
Title: My Example Post
Date: 2025-08-24 15:00
Modified: 2025-08-24 15:00
Category: Examples
Tags: example, markdown, blog
Slug: example-post
Authors: John Doe
Summary: This is an example of a blog post.

# This is the main heading

This is a paragraph of text. You can use **bold**, *italic*, and other Markdown formatting.

## This is a subheading

- You can create lists.
- Like this one.
```

## Viewing Your Post Locally

To see how your post will look, you can build and serve the blog locally. Use the following commands from the root directory of the project:

```bash
pelican content
pelican --listen
```

Then, open your web browser and navigate to `http://localhost:8000` to see your blog.

## GitHub Actions Automation

This project uses GitHub Actions to automatically deploy the blog to GitHub Pages.

### Deploy Pelican Blog (`deploy-blog.yml`)

This workflow builds and deploys the blog.

-   **Trigger:** This action runs whenever a push is made to the `main` branch that includes changes to any `.md` file within the `content/` directory.
-   **Action:**
    1.  It installs the necessary Python dependencies (Pelican and Markdown).
    2.  It builds the static blog using Pelican.
    3.  It deploys the generated site to GitHub Pages.
