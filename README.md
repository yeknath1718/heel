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





8.Installing and Running Nagios with Docker:



A) Install Nagios using Docker:
1. Open DockerHub and pull the Nagios image. docker pull nagios
B) Run Nagios Container, Open Browser, and Monitor Localhost:
1. Run the Nagios container with the following command: docker run -p 8888:80 --
name nagios-container -d nagios
• This maps port 8888 on the host to port 80 on the Nagios container.
2. Access Nagios by opening the browser and typing localhost:8888.
3. Login to Nagios using the following credentials:
• Username: nagiosadmin
• Password: nagios
4. Nagios Dashboard Overview:
• Observe Nagios dashboard, ensuring successful installation.
5. Monitoring Hosts:
• Click on "Hosts" on the left-side list to observe the current network status.
• Verify the status of the localhost and associated services.
6. Monitoring Service Groups:
• Explore various service groups by clicking on the relevant options.
7. Stopping the Nagios Container:
• When monitoring is complete, stop the Nagios container using the following: 
docker stop nagios-container




9.Working with Docker:


A) Pulling and Running Nginx, TomEE, and Wordpress Services:
1. Install Docker Desktop:
• Ensure Docker Desktop UI is open.
• Confirm Docker version with docker --version.
• View available images: docker images.
• Check all containers: docker ps -a.
2. Pull and Run Nginx, TomEE, and Wordpress:
• Pull Nginx: docker pull nginx.
• Pull TomEE: Specify TomEE image pull command.
• Pull Wordpress: Specify Wordpress image pull command.
• Run Nginx: docker run -p 80:80 --name nginx-container -d nginx.
• Run TomEE: Specify TomEE container run command.
• Run Wordpress: Specify Wordpress container run command.
3. Verify and Access Services:
• Open your browser and visit localhost to view Nginx.
• Access TomEE and Wordpress services per the specified configurations.
B) Use Docker Compose with Dockerfile:
1. Create Dockerfile:
• Use vim Dockerfile to craft and refine your Dockerfile.
• Define necessary configurations and dependencies.
2. Build Docker Image using Dockerfile:
• Execute: docker build -t custom-image ..
3. Run Container from Custom Image:
• Run: docker run -p custom-port:internal-port --name custom-container -d 
custom-image.
C) Use Docker Compose with YAML File:
1. Understand Docker Compose:
• Docker Compose is a tool to define and run multi-container Docker 
applications.
• Configuration is done in a docker-compose.yml file.
2. Create docker-compose.yml:
• Use vim docker-compose.yml to tailor the YAML file.
• Define services, networks, and configurations in a clear structure.
3. Compose File Structure:
• version: Specifies the format of the docker-compose file.
• services: Describes the containers, their configurations, and dependencies.
• networks: Defines networks that containers will use to communicate.
• volumes: Specifies volumes for persistent data.
4. docker-compose.yml for Nginx and TomEE:
yamlCopy code
version: '3' services: nginx: image: nginx ports: - "80:80" tomee: image: tomee 
5. Run Containers with Docker Compose:
• Execute: docker-compose up -d.
• Docker Compose reads the docker-compose.yml file and starts the defined 
services.
6. Access Services Defined in Docker Compose:
• Visit localhost for Nginx.
• Access TomEE on the specified port.
7. Stop and Remove Containers Defined by Compose:
• Execute: docker-compose down.
8. Scaling a Service with Compose:
• Execute: docker-compose up -d --scale service-name=num-instances.
Docker Commands Overview:
• Pull Image: docker pull image-name.
• Run Container: docker run options image-name.
• List Images: docker images.
• List Containers: docker ps -a.
• Interactive Terminal: docker exec -it container-id /bin/bash.
• Tag and Push Image to Docker Hub:
• docker tag local-image username/repository:tag.
• docker push username/repository:tag.
Vim Section:
• Edit Dockerfile with Vim:
• Use vim Dockerfile to open and edit.
• Navigate with arrow keys.
• Press i to enter insert mode.
• Edit and press Esc to exit.
• Type :wq to save and exit.
• Enter Interactive Terminal with Vim:
• Run: docker exec -it container-id /bin/bash.
• Navigate using cd.
• Edit a file with vim.
• Press i for insert mode.
• Edit, then press Esc.
• Type :wq to save and exit




10.Kubernetes Setup:

Step 1: Search for Minikube install on Google. Click on the highlighted link as shown.
Step 2: Ensure the following options are highlighted and click on the latest release to 
download the executable file.
Step 3: Download the Minikube installer, select the preferable language (English).
Step 4: Click on Next and agree to the license.
Step 5: Choose the installation path, complete the installation, click on Next, and finish.
Step 6: Open the command prompt/Windows PowerShell in administrative mode and run 
minikube start.
Step 7: If an internal command error occurs, set the path in environmental variables. Copy 
the Minikube path.
Step 8: Open Environmental Variables -> Double-click on the Path in System variables -> 
Paste the copied path -> Click OK.
Step 9: Restart the command prompt/Windows PowerShell and run minikube start again.
Step 10: Open Windows PowerShell in Administrator Mode and log in to Docker.
Step 11: Start Minikube using Hyper-V, Docker, or VM (VirtualBox):
• minikube start --vm-driver=virtualbox (if using only Minikube start, the default driver 
is used)
Step 12: Check Minikube status: minikube status.
Deploying and Managing Applications:
Step 13: Deploy an application in Kubernetes: kubectl create deployment mynginx --
image=nginx.
Step 14: Check deployments: kubectl get deployment.
Step 15: Check running pods: kubectl get pods.
• Status may show "ContainerCreating."
Step 16: Display detailed pod information:
• kubectl describe pods
Step 17: Scale deployment to 4 replicas:
• kubectl scale deployment mynginx --replicas=4
Step 18: Check deployment instances: kubectl get deployment.
Step 19: Check running pods: kubectl get pods.
Step 20: Describe a specific pod:
• kubectl describe pod mynginx6b78685d4dhrc9h
Step 21: Provide additional details if needed.
Step 22: Expose deployment to NodePort:
• kubectl expose deployment mynginx --type=NodePort --port=88
Step 23: Get service URL with Minikube:
• minikube service mynginx --url
Step 24: Copy and paste the generated URL.
Step 25: Nginx server is now accessible.
Step 26: Open Kubernetes Dashboard with Minikube:
• minikube dashboard
Step 27: Access the Minikube Dashboard.
Step 28: Delete deployment:
• kubectl delete deployment myngnix1
This sequence of steps ensures the setup, deployment, scaling, and management of 
applications within a Kubernetes cluster using Minikube
