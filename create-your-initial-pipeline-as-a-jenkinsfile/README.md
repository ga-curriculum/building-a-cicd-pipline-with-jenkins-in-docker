<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Create Your Initial Pipeline as a Jenkinsfile</span>
</h1>

**Learning Objective:** By the end of this lesson, students will be able to create an initial Jenkins pipeline using a Jenkinsfile.

## Create your initial pipeline as a Jenkinsfile

You’re now ready to create your Pipeline that will automate building your Node.js and React application in Jenkins. Your Pipeline will be created as a Jenkinsfile, which will be committed to your cloned Git repository (simple-node-js-react-npm-app).

### What is a Jenkinsfile?

A **Jenkinsfile** is a text file that defines the steps of a Jenkins Pipeline. It is stored in your version control system, making your pipeline versioned and reviewable like any other part of your codebase. This practice is known as **Pipeline-as-Code**.

For more details, check out the **Pipeline** and **Using a Jenkinsfile** sections in the **[Jenkins User Handbook](https://www.jenkins.io/doc/book/)**.

Now, let’s create your initial Jenkins Pipeline to automate building your application.

### 1. Create a Jenkinsfile

1. Open **VS Code**.
2. Navigate to the root directory of your cloned Git repository (`simple-node-js-react-npm-app`).
3. Create a new file named `Jenkinsfile`.

### 2. Add a `Build` stage to your Jenkinsfile

Copy the following Declarative Pipeline code and paste it into your empty `Jenkinsfile`:

```plaintext
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
    }
}
```

- **Agent:** The `agent any` directive specifies that the pipeline can run on any available Jenkins agent.

- **Stages and Steps:** The `Build` stage contains a single step to install the application’s dependencies using the `npm install` command.

### 3. Save and commit your changes

1. Save the `Jenkinsfile`.
2. In your terminal, navigate to the `simple-node-js-react-npm-app` directory, and run the following commands to commit and push your changes to Git:

```sh
git add .
git commit -m "Add initial Jenkinsfile"
git push
```

### 4. Run the pipeline in Jenkins

1. Go back to Jenkins and log in if necessary.

2. Navigate to your previously created Pipeline project.

3. Run the pipeline by clicking the `Build Now` button.

## Observing the pipeline execution

Once the pipeline starts, you’ll see a job appear in the Jenkins Build Queue on the left.

1. Click on the job name to view details.

2. Jenkins will process the tasks defined in your pipeline:
   - It will pull your code from the Git repository.
   - It will run the `npm install` command to install dependencies.
