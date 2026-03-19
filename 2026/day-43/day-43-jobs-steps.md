Task 1:
name: Multiple Jobs

on: workflow_dispatch

jobs:
  Build:
    runs-on: [self-hosted, linux, x64]
    steps:
      - name: Building app
        run: echo "Building app!"
  Test:
    runs-on: [self-hosted]
    needs: Build
    steps:
      - name: Testing the app
        run: echo "Testing the app!"
  Deploy:
    runs-on: [self-hosted]
    needs: Test
    steps:
      - name: Deploying the app
        run: echo "Deploying app!"

TASK 2:
name: Environment Variables

on: push

jobs:
  Print_Env_variable:
    runs-on: [self-hosted]
    steps:
      - name: Workflow level
        env:
          APP_NAME: "myapp"
        run: echo "Workflow level - $APP_NAME"
      - name: job level
        env:
          ENVIRONMENT: "staging"
        run: echo "Job Level - $ENVIRONMENT"

      - name: Step level
        env:
          VERSION: "1.0.0"
        run: echo "Step Level - $VERSION"

      - name: Commit SHA
        run: echo " Commit SHA - ${{ github.sha }}"

      - name: Actor name
        run: echo "Actor name - ${{ github.actor }}"
