<p align="center">
<img src="https://github.com/kura-labs-org/kuralabs_deployment_1/blob/main/Kuralogo.png">
</p>
<h1 align="center">C4_deployment-1<h1> 

Demonstrate your ability to run a Jenkins build and manually deploy to Elastic Beanstalk.

- Create a separate GitHub repository for this application 

- Download the files from this repository and upload them to your newly created repository 

- Be sure to follow the deployment instructions from this Repository  

- Document your progress in a .md file in your repository. Also, document any issues you may run into and what you did to fix them.

- Lastly, save your documentation and diagram into your repository. Submit your repository link to the LMS

## Deployment instructions Link:
-  Link to instructions: https://github.com/kura-labs-org/c4_deployment-1/blob/main/Deployment-instructions.md


# Documentation: GitHub Repository Setup

## Initial Setup
- Copied files from the `deployment1-main` folder from Kura Labs GitHub
- Created a new repository in my GitHub account named `Deployment1`
- Downloaded ZIP files from the repository

## Jenkins Setup
1. Logged into the instructor's Jenkins server
2. Clicked on "New Item"
3. Named the item `Khalil_E`
4. Selected "Pipeline" and clicked "OK"
5. Added a description
6. Selected "Pipeline script from SCM" in the Pipeline dropdown
7. Selected "Git" in the SCM dropdown
8. Added my repository URL from GitHub to the Repository URL field in Jenkins
9. Added credentials:
   - Clicked "Add" > "Jenkins"
   - Added my GitHub account username
10. Generated a token in GitHub:
    - Settings > Developer Settings > Personal access token
11. Added required permissions to the token
12. Copied the token and pasted it in the password field in Jenkins
13. Added "Github" in the ID field
14. Added a description and clicked "Add"
15. Selected my newly created credentials in the dropdown
16. Switched the Branch Specifier to `./main` in the Branch to Build section
17. Clicked "Apply" and "Save"
18. Clicked "Build Now" to start the build

## Build and Test
Stage view of the build:
- Checkout SCM
- Build & test were successful with no failures
- Executed bash commands to run a Python testing environment
- Installed and updated dependencies using pip
- Exported into Flask to build the application

In the test stage, bash commands were used to:
- Navigate to the source of the testing environment
- Conduct `py.test` and produced test results

The pipeline was successful, and the application files were downloaded in a ZIP file from the repository.

## AWS Deployment
Navigated to AWS account console:
- Clicked "Roles"
- Created two roles: `aws-elasticbeanstalk-service-role` and `Elastic-EC2`
- Assigned necessary permissions to the roles

Created an Elastic Beanstalk application:
- Selected the application name: `url-shortener`
- Chose the platform: `Python 3.9 running on 64bit Amazon Linux 2023`
- Uploaded the application code ZIP file
- Configured instance profile, VPC, availability zone, volume type, and instance type
- Submitted the application

Resolved issues with environment health and achieved successful deployment.
