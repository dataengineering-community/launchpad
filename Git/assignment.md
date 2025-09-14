## 1. Repository Creation

- Create a GitHub repository named **data-engineering-toolkit** and initialize it with a README file.  
- Clone the repository to your local machine.  
- Set up a `.gitignore` file to exclude unnecessary files (e.g., `*.pyc`, environment files).  
- Write a README that describes the purpose of the project and includes sections for:  
  - Documentation  
  - Code examples  
  - Contribution guide  

---

## 2. Set Up Branching Strategy

- Adopt a branching strategy. For this project, use the **Gitflow model**:  
  - **Main** branch for stable, production-ready code.  
  - **Develop** branch for integration.  
  - **Feature branches** (`feature/branch-name`) for new features or scripts.  

- Set up branch protection rules on GitHub for the **main** branch to require pull requests before merges.  

---

## 3. Develop Scripts on Feature Branches

- Choose three features that each represent a data engineering task. Examples:  
  1. **Data Cleaning Script** – Automate basic data cleansing functions.  
  2. **Data Transformation Script** – Create functions to apply transformations to data frames.  
  3. **Data Loading Script** – Create functions that write data to file.  

- Create separate feature branches for each toolkit script.  
- Develop each script on its respective branch, committing frequently.  

---

## 4. Pull Request and Code Review Process

- Once a feature is ready, push the branch to GitHub.  
- Open a pull request (PR) from the feature branch to the **develop** branch. Ensure your PR description includes:  
  - Summary of changes.  
  - Code examples or screenshots.  
  - Any testing instructions.  

- Set up a code review with at least one other developer (or review your own code with comments for practice).  
- Address any code review comments and iterate by pushing updates to the feature branch.  
- Once approved, merge the PR to **develop**.  

---

## 5. Merging to Main and Releasing Versions

- Periodically merge the **develop** branch into **main**.  
