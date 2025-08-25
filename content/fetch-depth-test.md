Title: Fetch Depth Test
Date: 2025-08-25 20:50
Category: Testing
Tags: fetch-depth, workflow, fix
Slug: fetch-depth-test
Authors: DS
Summary: Testing if fixing the fetch depth resolves the workflow issue.

# Fetch Depth Test

This test should work now that we've set `fetch-depth: 2` in the checkout action, which will allow `git diff-tree` to compare against the parent commit.