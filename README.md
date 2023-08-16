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


Documentation:
Copied files from deployment1-main file from kura labs github
Created a new repository in my github account named Deployment1
Downloaded Zip files from repository
Logged into instructors Jenkins server
Clicked on "New Item"
Named item Khalil_E
Selected "Pipeline"
Clicked Ok
Added Description
Scrolled down to Pipline and selected "Pipeline script from SCM" in dropdown
On SCM dropdown I selected "Git"
Added My respository URL from github to the Repository URL field in Jenkins
Added credentials: Clicked Add>Jenkins> Added my github acct username> for password I generated a token
Went to github and selected "Settings"
Under Settings I selected Developer Settings
In Developer settings, I selected personal access token (classic) > Generate a new token (classic)
Added on repo & adminrepo hook
Generated the token
Copied token and pasted it in the password field in Jenkins
in the ID field I added Github
Added Description
Clicked "Add"
In credentials dropdown I selected my newly created credentials
Scrolled down to Branch to Build and switched the Branch Specifier to "./main"
Clicked "Apply" and "Save"
Clicked "Build Now" to start my build
Stage view of my build populated; Checkout SCM, Build & test were all successful. No failures
In the Build, there were bash commands to run a python testing environment, then navigated to the source where the testing environment was taking place. pip installed to ensure everything was updated & compiled. Exported into FLASK to build the application
In the Test, there were bash commands that went to the source of the testing environment to conduct a py.test and produced results of the test
Pipeline was successful, so I downloaded the application files in a zip file from my repository & opened the scribe link
Navigated to aws account console
Clicked "Roles"
Clicked "Create role"
Clicked the "AWS serviceAllow AWS services like EC2, Lambda, or others to perform actions in this account." field.
Clicked Use cases for other AWS Services
Selected "Elastic Beanstalk"
Clicked the "Elastic Beanstalk - CustomizableAllows Elastic Beanstalk to create and manage AWS resources on your behalf." field.
Clicked the "Role name" field and entered "aws-elasticbeanstalk-service-role"
Clicked "Create role"
Clicked "Create role" to create a second Role
Clicked the "AWS serviceAllow AWS services like EC2, Lambda, or others to perform actions in this account." field.
Clicked the "EC2Allows EC2 instances to call AWS services on your behalf." field.
Scrolled to Permissions Policies
Clicked the "Filter policies by property or policy name and press enter." field and found "AWSElasticBeanstalkWebTier" and checked the corresponding box
Clicked the "Filter policies by property or policy name and press enter." field and found (AWSElasticBeanstalkWorkerTier). 
No results were found. I realized the filter for "AWSElasticBeanstalkWebTier" was still active in my search. I clicked the "X" next to "AWSElasticBeanstalkWebTier" to clear it out
I re-entered AWSElasticBeanstalkWorkerTier, and clicked the checkbox next to the AWSElasticBeanstalkWorkerTier policy
Cleared the filter then Clicked the "Filter policies by property or policy name and press enter." field and found "AWSElasticBeanstalkMulticontainerDocker" & clicked the checkbox for the policy
Clicked "Next" 2x
Clicked the "Role name" field and entered "Elastic-EC2"
Clicked "Create role"
Navigated to https://us-east-1.console.aws.amazon.com/elasticbeanstalk/home?region=us-east-1#/welcome
Clicked "Create application"
Clicked the "Application name" field.
Type "url-shortener"
Clicked Platform
Clicked "Python"
Clicked (Platform branch)
Clicked "Python 3.9 running on 64bit Amazon Linux 2023"
Clicked the upload code button.
Clicked the "Version label" field.
Typed "v1"
Clicked the local file button.
Clicked "Choose file" and uploaded my zipped file
Clicked "Next"
Clicked (EC2 instance profile) & Selected ElasticEC2 from the dropdown
Clicked "Next"
Clicked (VPC) dropdown and selected my default VPC
Selected us-east-1a Availability Zone
Clicked "Next"
For "Root Volume Type" I selected "General Purpose (SSD)" & changed the size field from 8 to 10
Scrolled down to "Instance Types" & deselected the types that were pre-populated
Added t2 micro instance
Clicked "Next"2x & then "Submit"
Waited for my environment to complete, but when the link produced, the "Health" status was "Degrading" and produced a 502 error for "Bad Gateway."
Created a new environment called v_1
Followed all the same steps but I uploaded a zip file that I extracted and then compressed again
When the environment was created, the health was still "Degrading"
I realized that the zip file I uploaded had an issue. When you open it, it leads to another zip file first, rather than opening the application files. It opened to the zip file within the zip file.
I created a new environment called "v2" but this time I extracted the application files from the zip file. I then selected the specific files I wanted in the zip file and compressed those. I noticed there was a folder with the same name as my zip file present within the files I extracted. I made sure not to add that folder, to my new compressed file, & uploaded that file to the environment.
Followed the steps from above and waited for the environment to create
Once the link was produced this time, Health status read "OK" and the link took me to the URL-shortener site successfully.
