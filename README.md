name: Automate Issues

on:
  issues:
    types:
      - opened

jobs:
  automate-issues:
    runs-on: ubuntu-latest

    steps:
      - name: Create Project Issue
        uses: actions/github-script@v5
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          script: |
            const issueTitle = context.payload.issue.title;
            const issueBody = context.payload.issue.body;

          
        

            console.log(`Issue "${issueTitle}" created in the project.`);
