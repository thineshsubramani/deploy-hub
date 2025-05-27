# Deploy-Hub: My Personal CI/CD Hub
Deploy-Hub is my go-to for managing builds and deployments across all my GitHub repos using my 1-2 self-hosted runners. It handles building packages, creating releases, updating READMEs and GitHub Pages, and publishing to apt, snap, pacman, and more. The magic happens in a public composite action that anyone can use for their own projects. It also tracks which repos use it and their build status.

## How It Works
My repos (like my-username/my-app) push a tag or send a webhook to trigger deploy-hub.
Deploy-Hub uses my runners to build packages, make GitHub releases, update repo assets, and publish to package managers.
A report logs which repos ran and if builds succeeded or failed.
The composite action (action.yml) is reusable for anyone to build, release, and publish their projects.

## Using My Composite Action
Want to use the same setup? Grab my composite action for your workflows:

### Add it to your GitHub workflow:
Use your-username/deploy-hub@action.
Set inputs like repo name, version, and build commands.


Make sure you have a GitHub token and package manager credentials.
Run it on your own runners or GitHub-hosted ones.

## Setup (For Me)

My runners are set up in deploy-hub with tools for building (debhelper, snapcraft, etc.).
Source repos trigger deploy-hub with a simple workflow or webhook.
Reports are saved as GitHub Issues for tracking.

## For Others
My composite action is public! Check action.yml to use it for your own builds, releases, or package publishing. It’s flexible and ready to go!
Questions? Hit me up via GitHub Issues!
