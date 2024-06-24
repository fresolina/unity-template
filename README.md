# Unity template

Template for a URP Unity project.

## Goals

* Minimize load time when creating a new project.
* Setup for VSCode
* Code formatting and linting
* Add minimal nice-to-have addons for all Unity projects

## What has been done?

* Minimize amount of packages in manifest.json
* VSCode recommendations and debug setup
* Custom "Create script" template, for less bloat.
* .editorconfig setup
* VSCode setup, filtering out unnecessary files in the explorer

## Mini-guide for GameCI: <https://game.ci/docs/github/activation>

1. Possibly update .github/workflows/unity-build.yml:unityVersion
2. Add secrets to GitHub
Find Unity license file:
    Windows: C:\ProgramData\Unity\Unity_lic.ulf
    Mac: /Library/Application Support/Unity/Unity_lic.ulf
    Linux: ~/.local/share/unity3d/Unity/Unity_lic.ulf
Create the following secrets: Settings -> Secrets and variables -> Actions -> New repository secret
    UNITY_LICENSE - (Copy the contents of your license file into here)
    UNITY_EMAIL - (Add the email address that you use to login to Unity)
    UNITY_PASSWORD - (Add the password that you use to login to Unity)
3. Add itch.io secret:
    Create a new API key at <https://itch.io/user/settings/api-keys>
    Create a new secret in the repository called BUTLER_CREDENTIALS
Update Deploy step. Change ITCH_GAME, ITCH_USER
