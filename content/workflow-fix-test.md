Title: Testing Workflow Fix
Date: 2025-08-25 20:45
Category: Testing
Tags: workflow, fix, github-actions
Slug: workflow-fix-test
Authors: Kiro
Summary: Testing the fixed workflow sequence to ensure auto-generated entries are properly included in the deployed site

# Testing Workflow Fix

This post is created to test the fixed workflow sequence where:

1. Auto-blog workflow creates auto-generated entries first
2. Deploy workflow waits for auto-blog completion
3. Site is built with all content including auto-generated entries

## Expected Behavior

- Auto-generated blog entry should be created
- Deploy should happen after auto-blog completion
- Final site should include both this post and the auto-generated entry

Let's see if this works!