# devops-helloworld
CI/CD Tutorial for class presentation

Based on [this tutorial](https://spacelift.io/blog/github-actions-tutorial).


## Homework Design

The objective is to add a Github Action that logs into your Docker account, to the existing go.yml file. 

### Docker Account
If you do not have a Docker account, create one [here](https://www.docker.com/).
### Modify the current `go.yml` file 
Add
```
    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v1

    - name: Login to Docker Hub
      uses: docker/login-action@v2
      with:
        username: ${{ secrets.DOCKER_USERNAME }}
        password: ${{ secrets.DOCKER_PASSWORD }}
```
### Configure GitHub Secrets:

  In your GitHub repository, navigate to "Settings" > "Secrets" > "New repository secret".
  
  Create a new secret named **DOCKER_USERNAME** with your Docker Hub username.
  
  Create another secret named **DOCKER_PASSWORD** with your Docker Hub password.

  Commit the `go.yml` file, and push the changes to GitHub.

### Verify the Pipleline

Open your GitHub repository in a browser.

Navigate to the "Actions" tab to monitor the workflow's progress.

Ensure that the pipeline runs successfully.

### Submission

Submit the URL of your GitHub repository to knguyen07@email.wm.edu 
