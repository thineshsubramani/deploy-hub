# Deploy-Hub: My Personal CI/CD Hub
Deploy-Hub centralizes builds and deployments for all my GitHub repos using my 1-2 self-hosted runners. Since personal GitHub accounts don’t support runner groups, this hub consolidates CI/CD tasks—building packages, creating releases, updating READMEs and GitHub Pages, and publishing to apt, snap, pacman, and more—in one place. The core logic is in a public composite action that anyone can reuse. It also tracks which repos use it and their build status.

## How It Works
- Multiple repos trigger deploy-hub to handle their CI/CD:
```
my-repo1 ----> Deploy-Hub <---- my-repo2
   |                            |
   +----> Builds, Releases, Publishes <----+
```
- My repos (like my-username/my-app) push a tag or send a webhook to trigger deploy-hub.
- Deploy-Hub uses my runners to build packages, make GitHub releases, update repo assets, and publish to package managers.
- A report logs which repos ran and if builds succeeded or failed.
- The composite action (action.yml) is reusable for anyone to build, release, and publish their projects.

## Using My Composite Action
### Want to use my setup? Grab the composite action:
- Add to your workflow: [WIP] your-username/deploy-hub@action.
- Set inputs (repo, version, build commands).
- Use a GitHub token and package manager credentials.
- Run on your runners or GitHub’s.

## Setup (For Me)
- Runners in deploy-hub have tools (debhelper, snapcraft, etc.).
- Repos trigger deploy-hub via workflows or webhooks.
- Reports are saved as GitHub Issues.

## For Others
My composite action is public! Check action.yml to use it for your own builds, releases, or package publishing. It’s flexible and ready to go!
Questions? Hit me up via GitHub Issues!
