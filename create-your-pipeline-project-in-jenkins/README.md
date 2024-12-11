<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Create Your Pipeline Project in Jenkins</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to set up a basic Jenkins pipeline project using version control.

## Create your pipeline project in Jenkins

Follow these steps to create your first Pipeline project in Jenkins. This will set the foundation for building, testing, and deploying applications with Jenkins.

### 1. Access Jenkins

Log in to Jenkins. If prompted, log in again. Once inside, look for the **create new jobs** option under the "welcome to jenkins!" section.

- If you don’t see this, click **new item** at the top left of the page.

### 2. Name your pipeline project

In the **enter an item name** field, specify a name for your new pipeline project. For this lesson, use `simple-node-js-react-npm-app`.

### 3. Select pipeline project type

Scroll down, select **pipeline**, and then click **ok** at the bottom of the page.

### 4. Add a description (optional)

On the next page, you can add a brief description in the **description** field. For example:  
_an entry-level pipeline demonstrating how to use jenkins to build a simple node.js and react application with npm._

### 5. Access the pipeline configuration tab

At the top of the page, click the **pipeline** tab. Scroll down to the **pipeline** section.

### 6. Define the pipeline script source

In the **definition** field, choose **pipeline script from scm**. This tells jenkins to fetch the pipeline script from your version control management (scm) system, which in this case is git.

### 7. Configure Git as the scm

In the **scm** field, select **git**.

### 8. Provide the repository url

In the **repository url** field, enter the browser url for the main page of your `simple-node-js-react-npm-app` repository.

### 9. Add credentials

If this is your first time connecting jenkins to github, you’ll need to add credentials. In the **credentials** dropdown menu, select **jenkins credential**. This will open a new popup window.

### 10. Choose credential type

In the popup, select **username and password** as the credential type.

### 11. Enter your GitHub Enterprise credentials

Fill in the fields with your github enterprise `username` and `password`.

### 12. Verify the connection

Once the credentials are added, jenkins will automatically test the connection to your repository. If successful, the red error message will disappear.

> If you encounter issues connecting jenkins to git, double-check the repository url and your credentials.

Now that your pipeline project is set up, you’re ready to explore how jenkins automates build processes step by step!
