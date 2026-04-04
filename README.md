Here creating this repo to learn concepts of GIT

Main Problem

Summary: Pushing to GitHub with a Personal Account on a Different laptop or account

What We Did

Step	Command	Purpose
1	git config user.name "JaiSharma-10"	Set local (repo-only) Git username
2	git config user.email "jaiintech@gmail.com"	Set local (repo-only) Git email
3	git remote set-url origin https://JaiSharma-10:TOKEN@github.com/...	Set remote URL with embedded PAT for authentication
4	git add . + git commit -m "Initial commit"	Stage and commit files
5	git push -u origin main	Push to GitHub and set upstream tracking

Concepts Used

	• Local vs Global Git Config — git config (without --global) writes to config inside the repo only. Your company credentials in the global config stay untouched.

	• Personal Access Token (PAT) — GitHub replaced password authentication with tokens. A PAT is generated from GitHub Settings and acts as a password with specific scopes (we used repo scope).

	• Token in Remote URL — Format: https://username:token@github.com/.... This bypasses Windows Credential Manager and VS Code's credential helper, which were defaulting to your company account.

	• -u flag (upstream tracking) — git push -u origin main links your local main branch to origin/main, so future pushes only need git push.

Key Takeaway
On a shared/company laptop, you can use repo-level config + PAT in the remote URL to work with a personal GitHub account without affecting any other projects.
<img width="1296" height="625" alt="image" src="https://github.com/user-attachments/assets/05617b9e-4106-49dd-a41e-97513999fd1a" />
