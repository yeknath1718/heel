1. ECLIPSE MAVEN JAVA PROJECT


Step 1: Create a New Maven Project in Eclipse
1. Open Eclipse IDE.
2. Navigate to File > New > Maven Project.
3. Set the Workspace location and click Next.
4. Choose the archetype as maven-archetype-quickstart.
5. Click Next and provide details like Group Id, Artifact Id, and Package.
6. Click Finish to create the Maven project.
Step 2: Set Up Maven Archetype
1. Select the archetype as maven-archetype-quickstart.
2. Click Next and provide details (Group Id, Artifact Id, etc.).
3. Click Finish to create the project using Maven archetype.
Step 3: Run Maven Goals in Eclipse
1. Right-click on the project in Eclipse.
2. Select Run As and go through the following Maven goals:
• Maven clean
• Maven install
• Maven test
• Maven build
3. Confirm the project creation by checking the console output.
Step 4: Run the Maven Project on Server
1. Right-click on the project.
2. Choose Run As > Run on Server to deploy and run the Maven project on a server.
Step 5: Push the Maven Java Project to GitHub
1. Create a new repository on GitHub.
2. Copy the HTTP link of the repository.
Using Git Bash:
1. Right-click on the project in Eclipse.
2. Select Show In > Local Terminal > Git Bash.
3. Initialize an empty Git repository with git init.
4. Add all files to the repository with git add ..
5. Commit all the files with git commit -m "Initial commit".
6. Add the GitHub repository as a remote with git remote add origin <repository_link>.
7. Push the files to GitHub with git push -u origin master.
Verify on GitHub to ensure that the files are successfully pushed.
These steps should cover the entire process from creating a Maven project in Eclipse to 
pushing it to a GitHub repository.



2.Eclipse Web Maven Project :


Step 1: Create a New Maven Project
1. Open Eclipse IDE.
2. Go to File > New > Maven Project.
3. Set up the Workspace location.
4. Click Next.
Step 2: Setting Up Archetype
1. Select the archetype as maven-archetype-webapp.
2. Click Next and provide Group Id, Artifact Id, and Package information.
• Group Id: Unique identifier for the project in a Maven repository.
• Artifact Id: Project name.
3. Click Finish to create the project.
Step 3: Configure Build Path
1. Right-click on the created project.
2. Choose Build Path > Configure Build Path.
3. Click on Add Library.
4. Add Server Runtime and select Tomcat 9.0.
5. Apply the changes and finish the configuration.
Step 4: Run Maven Project
1. Right-click on the project.
2. Select Run As and follow these steps:
• Maven clean
• Maven install
• Maven test
• Maven build
3. Finally, click on Run As > Run on Server.
Step 5: Maven Build Configuration
1. Click on maven build.
2. In the Edit Configuration and Launch window, enter clean install test in the Goals.
3. Click Apply and then Run.
Push the Maven Web Project to GitHub
3. Create a new repository on GitHub.
4. Copy the HTTP link of the repository.
Using Git Bash:
8. Right-click on the project in Eclipse.
9. Select Show In > Local Terminal > Git Bash.
10.Initialize an empty Git repository with git init.
11.Add all files to the repository with git add ..
12.Commit all the files with git commit -m "Initial commit".
13.Add the GitHub repository as a remote with git remote add origin <repository_link>.
14.Push the files to GitHub with git push -u origin master.
Verify on GitHub to ensure that the files are successfully pushed.
Now, your Maven web project should be pushed to GitHub




3.Pipeline for Maven Java Project using Jenkins:




Step 1: Set up Jenkins Jobs
1. Create java_build Job:
• Navigate to the Jenkins Dashboard and select "New Item."
• Name the project java_build.
• Choose the project type as "FreeStyle Project."
• Confirm by clicking OK.
2. Configure java_build Job:
• Under Source Code Management, choose Git.
• Provide your GitHub Repository URL.
• Set the Branch Specifier to */main.
• In Build Steps:
• Add a "Invoke top-level Maven targets" build step.
• Select MAVEN_HOME as the Maven version.
• Specify goals as "clean install."
• For Post-build Actions:
• "Archive the artifacts": Files to archive - "**/*".
• "Build other projects": Project name - java_test.
• Click Apply and Save.
3. Create java_test Job:
• Create a new item, name it java_test.
• Choose "FreeStyle Project" and click OK.
4. Configure java_test Job:
• In Build Environment, enable "Delete workspace before build starts."
• In Build Steps:
• "Copy artifacts from other projects": Artifacts to copy - "**/*".
• "Invoke top-level Maven targets":
• Set Maven version to MAVEN_HOME.
• Specify goals as "test."
• Click Apply and Save.
Step 2: Build Pipeline View
1. Create Build Pipeline View:
• From the Jenkins Dashboard, create a new view.
• Name it as desired and select "Build Pipeline View."
• Confirm by clicking Create.
2. Configure Build Pipeline View:
• Set the Initial Job to java_build.
• Save your configuration.
Step 3: Execute the Pipeline
1. Run the Pipeline:
• Access the created pipeline view.
• Click the "Run" button.




4.Pipeline for Maven-Web Project using Jenkins:


Step 1: Set up Jenkins Jobs
1. Create mavenbuild Job:
• Navigate to the Jenkins Dashboard and select "New Item."
• Name the project mavenbuild.
• Choose the project type as "FreeStyle Project."
• Confirm by clicking OK.
2. Configure mavenbuild Job:
• Under Source Code Management, choose Git.
• Provide your GitHub Repository URL.
• Set the Branch Specifier to */main.
• In Build Steps:
• Add an "Invoke top-level Maven targets" build step.
• Select MAVEN_HOME as the Maven version.
• Specify goals as "clean install."
• For Post-build Actions:
• "Archive the artifacts": Files to archive - "**/*".
• "Build other projects": Project name - maventest.
• Click Apply and Save.
3. Create maventest Job:
• Create a new item, name it maventest.
• Choose "FreeStyle Project" and click OK.
4. Configure maventest Job:
• In Build Environment, enable "Delete workspace before build starts."
• In Build Steps:
• "Copy artifacts from other projects": Artifacts to copy - "**/*".
• "Invoke top-level Maven targets":
• Set Maven version to MAVEN_HOME.
• Specify goals as "test."
• For Post-build Actions:
• "Archive the artifacts": Files to archive - "**/*".
• "Build other projects": Project name - mavendeploy.
• Click Apply and Save.
5. Create mavendeploy Job:
• Create a new item, name it mavendeploy.
• Choose "FreeStyle Project" and click OK.
6. Configure mavendeploy Job:
• In Build Steps:
• "Copy artifacts from other projects": Artifacts to copy - "**/*".
• "Invoke top-level Maven targets":
• Set Maven version to MAVEN_HOME.
• Specify goals as "deploy war/ear to a container."
• For Post-build Actions:
• "Deploy war/ear to a container":
• Enter war/ear files as "**/*.war".
• Enter context path as webpath.
• In containers, select Tomcat 9 and provide Tomcat URL.
• Click Apply and Save.
Step 2: Build Pipeline View
1. Create Build Pipeline View:
• From the Jenkins Dashboard, create a new view.
• Name it as desired and select "Build Pipeline View."
• Confirm by clicking Create.
2. Configure Build Pipeline View:
• Set the Initial Job to mavenbuild.
• Save your configuration.
Step 3: Execute the Pipeline
1. Run the Pipeline:
• Access the created pipeline view.
• Click the "Run" button.
Now, your Jenkins pipeline for the Maven-Web project is well-organized, covering all 
necessary build, test, and deployment stages. This structure ensures a seamless flow 
from project build to deployment on a Tomcat server.
