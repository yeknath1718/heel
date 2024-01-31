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
