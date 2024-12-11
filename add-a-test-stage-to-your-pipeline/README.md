<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Add a Test Stage to Your Pipeline</span>
</h1>

**Learning Objective:** By the end of this lesson, students will be able to expand their Jenkins pipeline by adding a test stage.

## Add a test stage to your pipeline

Testing is a critical step in the software development lifecycle. By automating tests in your pipeline, you:

- Ensure that changes to your code don’t introduce bugs or regressions.
- Build confidence in your application’s reliability before it reaches production.
- Save time by identifying issues earlier in the development process.

Adding a test stage to your pipeline allows Jenkins to run your test suite automatically as part of the build process.

### 1. Add a `Test` stage to your Jenkinsfile

Update the `Jenkinsfile` to include a new **Test** stage. Replace its contents with the following:

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
    }
}
```

Here’s what’s happening:

- **Build Stage:** This stage installs the application’s dependencies using `npm install`.
- **Test Stage:** A new stage runs a script (`test.sh`) to execute your test suite.
  - The `./jenkins/scripts/test.sh` path points to a custom shell script you’ve created for running tests.

### 2. Commit and push your changes

1. Save your updated `Jenkinsfile`.
2. Commit the changes to your Git repository:

```sh
git add .
git commit -m "Add test stage to Jenkinsfile"
git push
```

### 3. Run the updated pipeline

1. Go back to Jenkins and log in if needed.

2. Navigate to your Pipeline project.

3. Trigger a new build by clicking the `Build Now` button.

## Observing the Results

When the pipeline runs, Jenkins will execute the updated stages:

- **Build Stage:** Installs dependencies as before.
- **Test Stage:** Runs your test suite using the test.sh script.

You can monitor the pipeline's progress in the Jenkins console output. If the test stage encounters any errors, Jenkins will halt the pipeline and display the details to help you debug.
