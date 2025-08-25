Title: Testing Workflow Integration
Date: 2025-08-25 20:30
Category: Testing
Tags: workflow, github actions, testing
Slug: test-workflow-integration
Authors: DS
Summary: A test blog post to verify that our updated workflows work correctly together.

# Testing Workflow Integration

This is a test blog post created to verify that our GitHub Actions workflows are working correctly after the recent updates.

## What We're Testing

- Auto-blog workflow should trigger when this new markdown file is added
- It should create an auto-generated blog entry
- The deploy workflow should then build and deploy the updated site
- Both workflows should complete without conflicts

## Expected Behavior

1. Auto-blog workflow detects this new `.md` file
2. Creates an auto-generated entry in `content/auto-generated/`
3. Commits the auto-generated entry with `[skip-blog]` flag
4. Deploy workflow triggers on the commit and builds/deploys the site

Let's see if it works!