<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Add a Final Deliver Stage to Your Pipeline</span>
</h1>

**Learning Objective:**  By the end of this lesson, students will be able to expand their Jenkins pipeline by adding a final "Deliver" stage, interact with the application in a running environment, and demonstrate end-to-end pipeline automation.

## Add a final deliver stage to your pipeline

The deliver stage is the final step in your pipeline, where the application is deployed and ready for use.

This stage allows you to:

- Validate the end result of your build and test stages.
- Interact with the application in a live environment to ensure it works as expected.
- Practice simulating a production deployment scenario in a controlled environment.

### 1. Add a `Deliver` stage to your Jenkinsfile

Update the `Jenkinsfile` to include the new **Deliver** stage:

```groovy
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
```

Here’s what’s happening:

- **Deliver Script:** Executes the `deliver.sh` script, which deploys your application to a running environment.
- **Manual Input Step:** Jenkins pauses and waits for you to confirm (click "Proceed") before tearing down the running application.
- **Kill Script:** Executes the `kill.sh` script to stop the running application.

### 3. Commit and push changes

1. Save your updated `Jenkinsfile`.
2. Commit and push your changes to your Git repository:

```sh
git add .
git commit -m "Add deliver stage to Jenkinsfile"
git push
```

### 4. Run the pipeline

1. Go back to Jenkins and log in if necessary.
2. Trigger a new build by clicking the `Build Now` button.

## Viewing the application

1. When the pipeline reaches the **Deliver** stage, visit [http://localhost:3000](http://localhost:3000) in your web browser.
2. You should see your Node.js and React application running with the title **Welcome to React**.

> Tip: If you’re feeling a little adventurous, you can make changes to the application directly within the Jenkins Docker container.

To do this, run the following commands:

```sh
docker exec -it <docker-container-name> bash
cd /var/jenkins_home/workspace/simple-node-js-react-npm-app/src
vi App.js
```

- Replace `<docker-container-name>` with the name of your Jenkins container (use `docker ps` to find it, or it might default to `jenkins-tutorials` if you specified that name earlier).

- Edit the `App.js` file using the `vi` editor, save changes, and refresh the browser to see the updates reflected live.

## Completing the pipeline

1. After interacting with the application, return to Jenkins.
2. Click the **Proceed** button in the Jenkins UI to allow the pipeline to complete its execution.

## Wrap up

Congratulations! You’ve successfully built a Jenkins pipeline with a **Build**, **Test**, and **Deliver** stage for your Node.js and React application.

The pipeline you created is a foundation for automating more complex applications or deployments involving multiple technologies. Jenkins' flexibility means you can customize it to handle nearly any aspect of build and deployment orchestration.

<br>

<div class="activity discussion">
  <h2 class="title">Time to Reflect</h2>
  <span class="minutes">5 min</span>
</div>

Pipelines are powerful tools for automating workflows. Think about the steps you automated in this pipeline—how might this save time or prevent errors compared to manual processes?

Can you imagine applying similar automation to other repetitive tasks in your own work? Share your thoughts!
