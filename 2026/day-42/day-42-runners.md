TASK 1 _ Action on PR
** 
name: PR_Check

on:
  pull_request:
    branches:
      - main

jobs:
  PR_CHECK:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: PR check is running
        run: echo "PR check is running on BRANCH - ${{ github.head_ref }}"

TASK  2 _  Schedule
**
name: hello

on:
  schedule:
    - cron: "0 0 * * *"

jobs:
  Greet:
    runs-on: ubuntu-latest

    steps:
      - name: actions/checkout
        uses: actions/checkout@v4

      - name: Print Hello World
        run: echo "Hello from GitHub Actions!"

  system_info:
    runs-on: ubuntu-latest
    steps:
      - name: Print Current Date and Time
        run: echo "Current date and time - $(date)"

      - name: Print name of branch
        run: echo "Branch name - ${{ github.ref_name }}"

      - name: Print name of repository
        run: echo "Repository name - ${{ github.repository }}"

      - name: Print the list of files in the repository
        run: ls -l

      - name: Print the runner operating system
        run: echo "Runner OS - ${{ runner.os }}"

TASK 3 - Manual Trigger
**
name: Manual_Trigger

on:
  workflow_dispatch:
    inputs:
      name:
        description: "Environment name"
        required: true
        default: "staging"
        type: choice
        options:
          - staging
          - production

jobs:
  Manual_Trigger:
    runs-on: ubuntu-latest

    steps:
      - name: Print Environment Name
        run: echo "Environment name is - ${{ github.event.inputs.name }}"

