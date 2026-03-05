name: hello

on:
  push:

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
