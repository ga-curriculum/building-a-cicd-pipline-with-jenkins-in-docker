<h1>
  <span class="headline">Building a CICD Pipeline with Jenkins in Docker</span>
  <span class="subhead">Create Your Pipeline Project in Jenkins</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to set up a basic Jenkins pipeline project using version control.

## Create Your Pipeline Project in Jenkins

Follow these steps to create your first Pipeline project in Jenkins. This will set the foundation for building, testing, and deploying applications with Jenkins.

### 1. Access Jenkins:

Log in to Jenkins. If prompted, log in again. Once inside, look for the **Create new jobs** option under the "Welcome to Jenkins!" section.

- If you don’t see this, click **New Item** at the top left of the page.

### 2. Name Your Pipeline Project:

In the **Enter an item name** field, specify a name for your new Pipeline project. For this lesson, use `simple-node-js-react-npm-app`.

### 3. Select Pipeline Project Type:

Scroll down, select **Pipeline**, and then click **OK** at the bottom of the page.

### 4. Add a Description (Optional):

On the next page, you can add a brief description in the **Description** field. For example:  
 _An entry-level Pipeline demonstrating how to use Jenkins to build a simple Node.js and React application with npm._

### 5. Access the Pipeline Configuration Tab:

At the top of the page, click the **Pipeline** tab. Scroll down to the **Pipeline** section.

### 6. Define the Pipeline Script Source:

In the **Definition** field, choose **Pipeline script from SCM**. This tells Jenkins to fetch the Pipeline script from your version control Management (SCM) system, which in this case is Git.

### 7. Configure Git as the SCM:

In the **SCM** field, select **Git**.

### 8. Provide the Repository URL:

In the **Repository URL** field, enter the browser URL for the main page of your `simple-node-js-react-npm-app` repository.

### 9. Add Credentials:

If this is your first time connecting Jenkins to GitHub, you'll need to add credentials. In the **Credentials** dropdown menu, select **Jenkins Credential**. This will open a new popup window.

### 10. Choose Credential Type:

In the popup, select **Username and Password** as the credential type.

### 11. Enter Your GitHub Enterprise Credentials:

Fill in the fields with your GitHub Enterprise username and password.

### 12. Verify the Connection:

Once the credentials are added, Jenkins will automatically test the connection to your repository. If successful, the red error message will disappear.

> If you encounter issues connecting Jenkins to Git, double-check the repository URL and your credentials.

Now that your Pipeline project is set up, you’re ready to explore how Jenkins automates build processes step by step!
