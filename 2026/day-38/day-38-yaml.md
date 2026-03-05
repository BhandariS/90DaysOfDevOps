name: personal_info

on:
  workflow_dispatch:

jobs:
  personal_info:
    runs-on: ubuntu-latest

    steps:
      - name: User name
        run: echo "My name is Shubham"

      - name: User Role
        run: echo "I am a Salesforce DevOps Engineer"

      - name: Experience
        run: echo "I have 4 years of experience in Salesforce DevOps"

      - name: Learning
        run: echo "True"

  about:
        runs-on: ubuntu-latest
        needs: personal_info
        steps:
          - name: Print Tools
            run: echo
                - Jenkins
                - AutoRabbit
                - Github

        

--------------------------------------------------------------------------------------------------------------------


name: servers

on:
  workflow_dispatch:

jobs:
  server_info:
    runs-on: ubuntu-latest

    steps:
      - name: app_server
        run: |
          echo "App Server Info:"
          echo "IP Address: 192.168.1.100"
          echo "Port: 8080"
            run: echo [Cricket,Badminton,Gaming]
              
              
