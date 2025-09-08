# quiz-app
simple quiz app
A Professional GitHub Workflow: From Organization Setup to Pull Request Merging

This document summarizes the complete, real-world workflow we simulated, from the foundational setup of a GitHub organization to the final, secure merging of a pull request. This guide serves as a blueprint for implementing industry best practices to ensure code quality, accountability, and security within any team.

I. The Foundation: Building Your GitHub Organization

A GitHub organization is the central hub for professional development, providing the structure to manage members, teams, and access permissions at scale.1 As the organization owner, you have complete administrative control over this entire environment.2

Step 1: Create the Organization

This is the first and most critical step. The organization acts as the central account that will house all of your company's projects and members.

Step 2: Invite Members and Create Teams

In a real-world scenario, you will invite new developers, managers, and other team members to your organization.1 After inviting them, you'll organize them into logical groups, such as "Manager Team," "Development Team," and "DevOps Team".1 This team-based structure is a best practice for managing permissions efficiently.1

II. Securing Your Project: Repository and Governance

With your organization and teams in place, the next step is to create a project repository and establish a clear governance policy to protect your codebase.

Step 1: Create a Repository and Assign Team Roles

A repository is the central container where all project files and their history are stored. As the owner, you can create a new repository (e.g., quiz-app) and grant different levels of access to your teams.1
Admin: This role grants full access to a project, including managing branch protection rules and deleting the repository. You assigned this to the Manager Team.1
Write: This is the standard role for active developers who can push code to the repository. You gave this to the Development Team.1
Maintain: This role is for project managers who need to manage the repository without access to sensitive or destructive actions. You assigned this to the DevOps Team.1

Step 2: Implement Branch Protection Rules

This is the most crucial step for enforcing a professional workflow. You created a branch protection rule for the main branch to prevent direct pushes and require all changes to go through a formal review. The rule you set up was:
Require a pull request before merging: This ensures no one can push code directly to main.
Require approvals: This mandates that a pull request must receive a specified number of approvals from a reviewer before it can be merged.

Step 3: Create a CODEOWNERS File

This file is the final piece of your governance policy. By creating a CODEOWNERS file at the root of your repository, you designated your "Manager Team" as the required reviewer for all code changes. This enforces your policy of having a senior team member review and approve every pull request.
The syntax you used was:
* @dev-organization/manager-team.
The * symbol acts as a wildcard, applying the rule to every file in the repository. This ensures that even though a developer has Write permissions, the pull request cannot be merged until it is approved by a member of the "Manager Team".

III. The Developer Workflow: Making a Contribution

With the professional environment established, a developer can now work on a new feature with confidence.

Step 1: Clone the Repository

The developer begins by cloning the repository to their local machine using the git clone command. This creates a local copy of the project and its history.

Step 2: Create a Feature Branch

The developer creates a new branch for their work (e.g., feature/add-first-question) using the git checkout -b command. This isolates their changes and is a core practice of the "Feature Branch Workflow".

Step 3: Add and Commit Changes

The developer adds their new code, stages the changes with git add, and saves them to their local history with a descriptive message using git commit.3

Step 4: Push the Branch

Once the local commits are complete, the developer pushes the new branch to the remote repository using the git push command, making the changes visible to the rest of the team.

Step 5: Create a Pull Request (PR)

After pushing the branch, the developer navigates to GitHub to create a pull request. A pull request is a formal proposal to merge their code into the main branch, and it is the central mechanism for discussing and reviewing changes.

IV. The Final Steps: Review and Merge

This is the final phase of the workflow, where the security and governance you implemented are put into practice.

Step 1: Review is Automatically Requested

Because of the CODEOWNERS file, GitHub automatically notifies and requests a review from the "Manager Team". The "Merge pull request" button is disabled for the developer who created the PR, ensuring they cannot approve their own changes.

Step 2: The Reviewer Approves the Code

A member of the "Manager Team" reviews the code and, upon satisfaction, approves the pull request. Once this happens, the "Merge pull request" button turns green, signifying that all conditions have been met.4

Step 3: The Code is Merged

The final step is for an authorized person (e.g., a manager) to merge the pull request. The code from the feature branch is then securely integrated into the main branch, completing the cycle and ensuring the integrity of the project's history.
Works cited
Getting started with GitHub Team - GitHub Docs, accessed September 7, 2025, https://docs.github.com/en/get-started/onboarding/getting-started-with-github-team
Roles in an organization - GitHub Docs, accessed September 7, 2025, https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization
Git & GitHub - The Practical Guide | Academind, accessed September 7, 2025, https://pro.academind.com/p/git-github-the-practical-guide
GitHub Pull Requests from Start to Finish - Pluralsight, accessed September 7, 2025, https://www.pluralsight.com/courses/github-pull-requests-from-start-finish
