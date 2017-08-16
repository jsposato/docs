# Sonar file
## What file do I need in my project?
You need a sonar-project.properties file in the root of your repository.

## What goes in the file?
The file should contain configuration details for your project.
Example:
```
# must be unique in a given SonarQube instance
sonar.projectKey=com.weightwatchers.android
# this is the name displayed in the SonarQube UI
sonar.projectName=Android Tracker
sonar.projectVersion=1.0

# Path is relative to the sonar-project.properties file. Replace "\" by "/" on Windows.
# Since SonarQube 4.2, this property is optional if sonar.modules is set.
# If not set, SonarQube starts looking for source code from the directory containing
# the sonar-project.properties file.
sonar.sources=app/src/main/java/com/weightwatchers

# Encoding of the source code. Default is default system encoding
#sonar.sourceEncoding=UTF-8
```

# Sonar UI
## What groups need to exist?
At least a group per customer, if not per project or platform.

The jenkins user must be in the group in order for the scan at build time to work

## What permissions does the group get?
The group for the project/platform should have Browse rights only

# Jenkins setup

## What do I need to configure system-wide?
There shouldn't be any system-wide configuration if your Jenkins master was created by FIRE.

## What do I need to configure for a specific job?
For a job, you need to add a build step of 'Invoke Standalone SonarQube Analysis'

You can either create a sonar-project.properties in the root of your repository (preferred) or
configure the project properties in the job configuration

## How do I configure a job to run sonar on pull requests?
[Check Here](https://github.com/jsposato/docs/blob/master/Mobiquity/Sonar_Configuration_for_Pull_Requests.md)