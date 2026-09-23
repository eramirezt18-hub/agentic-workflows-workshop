---
name: Daily Digest
max-ai-credits: -1
model: gpt-4o
on:
  schedule: daily on weekdays
  workflow_dispatch:
permissions:
  contents: read
  issues: read
  pull-requests: read
network: defaults
safe-outputs:
  create-issue:
   
    max: 1
---

# Daily Digest

Every weekday, create a GitHub issue that summarises all open issues and
pull requests in this repository. Group them by label. Include the total
count, the title, the author, and how long each item has been open.

Title the issue "Daily Digest – <date>".

## Instructions

1. Fetch all open issues and open pull requests in this repository.
2. Group them by their labels. Items with multiple labels should appear
   under each of their labels. Items without labels should be grouped
   under "Unlabeled".
3. For each item, include:
   - The title
   - The author (GitHub username)
   - How long it has been open (e.g., "3 days", "2 weeks")
4. At the top of the issue, include a summary with the total count of
   open issues and the total count of open pull requests.
5. Format the output as a Markdown document with clear section headings
   per label group.
6. Title the created issue "Daily Digest – <today's date>".
