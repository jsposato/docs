## Configuring a job in Jenkins to run Sonar analysis
### Jenkins
1. The Jenkins master from FIRE will already have the main configuration completed.
2. In your Jenkins job, add a build step of 'Execute SonarQube Scanner'.
3. In your project, create a file in the root of your repository named sonar-project.properties.


### Sonar
1. The project will be created automatically on first analysis
2. Once created, the Sonar admin will need to create a group for the customer/project, associate
    group to Sonar app and add users to the group.


## Configuring a pull request job in Jenkins to run Sonar analysis
### Jenkins


### Sonar
