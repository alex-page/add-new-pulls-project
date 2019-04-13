# Add new pull requests to project

> ✨ GitHub action to automagically add new pull requests to projects.


# How to use

To use this action we need the project number and the name of the column for the new pull requests to go into. 
- Get the project number from the project URL `projects/1` the number would be `1`.
- Get the column name from the project board for example "To do".

In your project create a new workflow file `.github/main.workflow`:
```
workflow "✨Add new pull requests to projects" {
  resolves = ["alex-page/add-new-pulls-project"]
  on = "pull_requests"
}

action "alex-page/add-new-pulls-project" {
  uses = "alex-page/add-new-pulls-project@master"
  args = [ "1", "To do"]
  secrets = ["GITHUB_TOKEN"]
}
```

> Note: Replace `1` with your project number and `To do` with your project column.

# Release history

- v0.0.1 - First release