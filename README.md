# Python Lockfile Update

This action uses `pip-tools` to automatically build and update the `requirements.txt` files for a Python project.

## Permissions

### Github Token

A Github Token is for two purposes-

1. If a Deploy Key is not present then the Token is used to push the commit to Github.
2. Regardless of whether a Deploy Key is present, the Token needs to be available to make the Pull Request.

This project does not need a Personal Access Token, and in fact strongly recommends against it.

### Deploy Keys

Deploy Keys are optional but allow tests to be run in Pull Requests created by this action. If this action uses the normal Github token to push the code up then tests will not run on the Pull Request.

To get around this a [Deploy Key](https://docs.github.com/en/developers/overview/managing-deploy-keys) can be created for the repository running the action. The key will need write access to push up the commits, at which point the normal testing workflows should run.

This action will still work without the deploy key, but will fall back to the Github Token. The PR will be created but automated tests against it will not run.