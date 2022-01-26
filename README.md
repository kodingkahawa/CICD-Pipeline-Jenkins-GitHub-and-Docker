# CICD-Pipeline-Jenkins-GitHub-and-Docker
A Jenkins Pipeline that is triggered to build a Docker Image and push it Docker Hub upon a commit to the GitHub Repository
# Problem Statement
Build a complete automated deployment of a docker image of an application to a docker registry upon a commit to a GitHub repository
# Techstack
1. Jenkins - Automated build tool for all applications
2. Docker - To package and containerize the applications
3. GitHub - Code repositories and collaboration
# Workflow
1. Code changes are committed to the version control system – GitHub
2. Each commit to GitHub automatically triggers Jenkins build. Jenkins compiles the code, and can run unit test and perform additional checks – code coverage, code quality, etc.
3. Once the code has been successfully compiled and all the tests have been passed. Jenkins builds a new docker image and pushes it to the Docker registry (docker hub).
