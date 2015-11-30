# Sonar file
## What file do I need in my project?
You need a sonar-project.properties file in the root of your repository.

## What goes in the file?
The file should contain configuration details for your project.
Example:
```
# must be unique in a given SonarQube instance
sonar.projectKey=com.weightwatchers.mobile
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

## What permissions does the group get?

# Jenkins setup

## What do I need to configure system-wide?

## What do I need to configure for a specific job?
