# Creating a Jenkins Freestyle Project for Website Build

This guide will walk you through the process of setting up a Jenkins Freestyle project to build and deploy a website. Jenkins is an open-source automation server that can help streamline your development process by automating repetitive tasks like building, testing, and deploying your website.

## Prerequisites

- **Jenkins Installed**: Make sure you have Jenkins installed and running on your server or local machine. You can download Jenkins from the [official website](https://www.jenkins.io/download/) and follow the installation instructions.

- **Website Source Code**: Have your website source code hosted on a version control system like Git. You'll need the repository URL to configure Jenkins to pull the code.

## Steps

### 1. Create a New Jenkins Freestyle Project

1. Log in to your Jenkins dashboard.
2. Click on "New Item" to create a new project.
3. Enter a name for your project (e.g., "Website Build").
4. Select "Freestyle project" and click "OK".

### 2. Configure Source Code Management

1. Under the "Source Code Management" section, choose your version control system (e.g., Git).
2. Enter the repository URL of your website source code.
3. You can configure the branch you want Jenkins to build from.
4. You might need to provide authentication credentials if your repository is private.

### 3. Define the Build Steps

1. In the "Build" section, click on "Add build step" and choose the appropriate action for your website's build process. For a simple HTML/CSS/JS website, you might use shell commands to copy files and generate the necessary artifacts.

Example build steps:

```bash
# Assuming your website source code is in a directory named "src"
cd src
npm install   # If you're using Node.js
npm run build # If you're using a build tool like Webpack
```

### 4. Configure Post-Build Actions

1. In the "Post-build Actions" section, you can define what happens after the build completes.
2. For deploying your website, you can use tools like FTP, SCP, or even trigger another script.
3. For instance, to deploy to a web server via FTP:
   - Choose "Send files or execute commands over SSH" or "Publish Over SSH" depending on your Jenkins plugins.
   - Configure the connection to your server with the necessary credentials.
   - Define the source files to be transferred (e.g., from the build workspace) and the destination on the server.

### 5. Save and Run the Project

1. Click "Save" to save your project configuration.
2. You can manually trigger a build by clicking "Build Now" on the project page.
3. Jenkins will execute the defined build steps and post-build actions.

### 6. Set Up Polling or Webhooks (Optional)

1. You can configure your project to poll the repository for changes at regular intervals.
2. Alternatively, you can set up webhooks to trigger a build automatically whenever there's a new commit pushed to your repository.

## Conclusion

Congratulations! You've successfully set up a Jenkins Freestyle project to build and deploy your website. Jenkins will now automate your build process, making it easier to maintain and deploy your website with confidence.

Remember to adapt these instructions to your specific project's needs, tools, and technologies. Happy building! 🚀
