## Udacity - Udagram CI/CD Pipeline process
### CI/CD pipeline diagram

![CI/CD Pipeline diagram](./CICD%20pipeline%20architecture.png)

The pipline is triggered when code is pushed to Github. The pipeline workflow includes installing Node packages, linting, testing and deploying the code to the web server.

The pipeline consists of three stages:
1. **Build**: In this stage, we verify the code by checking coding conventions, run tests, and building the code. If any errors occur during this stage, the pipeline will stop and wait for the next code push.
2. **Hold**: If the build stage is successful, this stage waits for user approval. The next stage will only be triggered once this stage has been approved. Only the `main` or `master` branch can trigger this stage
3. **Deploy**: In this stage, the code is pulled to another container, followed by installing Node packages, building and deploying the code. We also update the configuration eviroment variables for the CI/CD project to complete this stage.