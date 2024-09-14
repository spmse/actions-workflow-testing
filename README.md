# Actions Workflow Testing

This repository was created to have a demonstration base and experimental playground for GitHub Actions.

## Overview

In order to see all defined [workflows](.github/workflows) or actions, refer to the corresponding subfolder in the `.github/` directory.

### Manual Workflows

To see how to create a manual callable workflow in github actions, see the [`manual-demo-workflow`](.github/workflows/manual-demo-workflow.yml)

The most important thing is to provide a correct trigger with the `workflow_dispatch` event, this allows you to run the workflow (complete workflow) on a manual basis from the GitHub Actions tab.

> [!IMPORTANT]
> Your workflow definition file needs to be placed in the default branch of the repository to make this work.
> If the file was contributed on a feature branch but not yet merged into the default, this will not work.

#### Defining a manual workflow

1. Copy & Paste the following example<sup>1</sup> code into a file in your testing repository under `.github/workflows/manual-proto.yml`
2. Save the file (Commit the changes)
    1. Ensure you are working on your repositories default branch
1. Go to the GitHub Actions Tab
2. Choose your workflow from the side
3. Choose a branch to run it for
4. Click on run

<details>
  <summary>
    <sup>1</sup> Example Workflow 
  </summary>

```yaml
# This is a basic workflow to help you get started with Actions
name: Manual-Workflow Demo

# Controls when the workflow will run
on:
  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "demo"
  demo:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v4

      # Runs a single command using the runners shell
      - name: Run a one-line script
        run: echo Hello, world!

      # Runs a set of commands using the runners shell
      - name: Run a multi-line script
        run: |
          echo Add other actions to build,
          echo test, and deploy your project.
```

</details>
