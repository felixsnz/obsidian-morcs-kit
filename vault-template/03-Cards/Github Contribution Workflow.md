---
up: 
tags:
  - guide
aliases: 
date: 2023-11-18
---

# Github Contribution Workflow

1. **Repository Fork**: You create a copy of the repository in your GitHub account. This gives you full control over your own copy of the project.
    
2. **Clone the Fork**: You download a local copy of your fork to your machine. This allows you to work on the project locally.
    
    `git clone [URL of your fork]`.
    
3. **Create a New Branch**: You create a new branch in your local repository. This is done to keep your changes separate from the main code (usually the `master` or `main` branch).
    
    `git checkout -b [your_branch_name]`.
    
4. **Make Changes**: You make your changes to the new branch. You can add, edit or delete files as needed.
    
5. **Commit and Push your Changes**: Save your changes to your branch and then upload them to your fork on GitHub.
    
    ```
	git add . git commit -m "Description of your changes"
    git push origin [your_branch_name]
    ```
    
6. **Create a Pull Request (PR)**: From your GitHub fork, you initiate a pull request to the original repository. Here you explain the changes you have made and why you think they should be incorporated into the main project.
    
7. **Review and Merge (Optional)**: The maintainers of the original project will review your PR. They may ask you to make additional changes, or they may accept your PR and merge your changes into the main project branch.