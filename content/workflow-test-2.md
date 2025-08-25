Title: Second Workflow Test
Date: 2025-08-25 20:35
Category: Testing
Tags: workflow, automation, success
Slug: second-workflow-test
Authors: DS
Summary: A second test to verify the auto-blog workflow triggers correctly for new files.

# Second Workflow Test

This is a brand new markdown file that should trigger the auto-blog workflow because it's being added for the first time.

The workflow should:
1. Detect this as a new `.md` file (status `A` in git)
2. Create an auto-generated blog entry
3. Commit and push the changes
4. Trigger the deploy workflow to build and deploy

Let's see if it works this time!