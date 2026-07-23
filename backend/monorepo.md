### Why is a monorepo better than two separate repos for this project?
A monorepo is better that 2 separate repos for this project because it keeps related code(our frontend and backend) in one place making it easier to share code, manage dependanceis and maintain consistency.

Developers can make changes across both parts of the application in a single commit, reducing coordination issues between repositories. It also simplifies project setup because a new developer only needs to clone one repository and follow one workflow.

---

### When would two separate repos be better? (Hint: different deployment cadences, different teams.)
two separate repositories may be better when the frontend and backend are managed by different teams, have different release schedules, or need to be deployed independently.

---

### What is the cost of a monorepo? (Hint: CI complexity, lockfile churn, unfamiliarity.)
The cost of using a monorepo is that the CI/CD pipeline can become more complex because it needs to handle multiple applications and workflows. Large monorepos can also experience lockfile conflicts and dependency update issues when many projects share the same configuration. Additionally, developers unfamiliar with monorepo tools and practices may face a learning curve when contributing to the project.