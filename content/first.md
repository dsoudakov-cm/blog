Title: How to Set Up Pelican for Your Blog
Date: 2024-04-15 10:00
Modified: 2024-04-15 10:00
Category: Tutorials
Tags: pelican, static site generator, python, blogging
Slug: setup-pelican
Authors: DS and ChatGPT
Summary: This tutorial walks you through setting up Pelican, a static site generator powered by Python, for your personal or professional blog.

# Setting Up Pelican for Your Blog

Pelican is a versatile static site generator that leverages Python to help you create blogs and websites quickly and with minimal configuration. Here's a step-by-step guide to setting up Pelican for your blog.

## Step 1: Install Python

Pelican is built on Python, so you need Python installed on your machine. It's recommended to use the latest Python 3 version. You can download it from the official [Python website](https://www.python.org/downloads/).

## Step 2: Install Pelican and Markdown

Once Python is installed, you can install Pelican and Markdown support using pip. Open your terminal and run:

```bash
pip install pelican markdown # install
pelican content # generate content (add md files to content folder first)
pelican --listen # serve locally
```