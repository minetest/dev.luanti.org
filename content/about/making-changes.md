---
title: Making Changes
---

# Making Changes

## Trivial Changes

_(for those with commit access)_

At the bottom of each page is an `edit this page` button. Clicking this will open up GitHub's web text editor where you can make text changes and commit. Alternatively you can use GitHub's VS Code interface from the repo page by clicking the `.` key.

## Significant Changes

_(for anyone)_

- Please fork the repo (for non-members of the repo, the `edit this page` option at the bottom of each page will walk you through this)
- Web-based
  - Once the repo is forked, go to the repo page and click `.`: this will open VS Code in the browser
  - Checkout a branch (bottom left, second option in)
  - Make your edits
  - In the left vertical menu, select the source control option
  - Enter a message about your changes and click `commit and push`
- Local-based (terminal commands for example, use GUI client if you wish)
  - Clone the repo `git clone https://github.com/YOURUSERNAME/dev.luanti.org`
  - Make a branch `git checkout YOUR_BRANCH_NAME`
  - Make edits with the tools of your choosing
  - Add, commit, and push the changes: `git add -A && git commit -m "YOUR COMMIT MESSAGE HERE" && git push`
- Make a PR from the branch back to the repo
- Wait for someone on the Luanti docs team to review and merge
