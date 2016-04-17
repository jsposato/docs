## Configuring a pull request job in Jenkins to run Sonar analysis
### Jenkins
1. Setup Github Pull Request Builder in Jenkins Configuration
   * Add firewrite user from the master configuration (needs to be username/password)

2. Setup PR job in Jenkins using Github Pull Request Builder
![alt text](https://github.com/jsposato/docs/blob/master/Mobiquity/images/PR_GitConfig.png "Git Config")

3. Configure the build trigger
![alt text](https://github.com/jsposato/docs/blob/master/Mobiquity/images/BuildTriggers.png "Build Trigger Config")

4. Add standalone sonar analysis
    * Need the following keys setup in the ‘Analysis Properties’ box:
        * sonar.analysis.mode=`incremental`
        * sonar.github.repository=`owner/repository`
        * sonar.github.pullRequest=`${ghprbPullId}`
        * sonar.github.oauth=`<Token For Github Access>`
            * Fire already has one for firewrite user

### Sonar
1. There is no special Sonar setup required.  The project should exist from the develop job.