## Configuring Jenkins to Use Google OAuth for Authentication

### Install Google Login Plugin
https://wiki.jenkins-ci.org/display/JENKINS/Google+Login+Plugin


### Install Role-based Authorization Strategy Plugin
https://wiki.jenkins-ci.org/display/JENKINS/Role+Strategy+Plugin


### Create Google OAuth token
This is not necessary since we are re-using the same token for all
Jenkins masters.  Google allows multiple origins and redirect URIs
for a token.

### Send request to add Jenkins master URLs to ITHelp@mobiquityinc.com
Be sure to include the following information:

origin: 

<JENKINS_URL>

and the authorized redirect URI should be:

<JENKINS_URL>/securityRealm/finishLogin

### Configure Jenkins
Be sure to configure both the Security Realm and authorization sections
![Git Config](https://github.com/jsposato/docs/blob/master/Mobiquity/images/SecurityConfiguration.png "Git Config")

The Jenkins URL needs to match the DNS name of the Jenkins master
![Jenkins URL](https://github.com/jsposato/docs/blob/master/Mobiquity/images/Configure_Jenkins_URL.png "Jenkins URL")

### Configure Roles
* Go to `Manage Jenkins->Manage and Assign Roles->Manage Roles`
* Add a role `authenticated` -> Must be named exactly like this
    * This role will be what users get by default when they login.
    * Assign the Overall Read permission
    * Assign Build, Cancel, Configure, Create, Delete, Discover, Move, Read, and Workspace in Job
    * Assign Configure, Create, Delete, and Read in View
* Add a role `anonymous`
    * This role will allow the transition from Oauth to the authenticated role
    * Assign the Overall Read permission
* Go to `Manage Jenkins->Manage and Assign Roles->Assign Roles`
    * Add your Mobiquity email address as an admin
    * Add the anonymous role to Anonymous
    * Save

###
Logout and login.  You should go through the Google authorization and then be logged in with admin rights.

Anyone at Mobiquity will be able to login and receive the rights granted by the `authenticated` role.  To
elevate someone's privileges, add them in `Assign Roles` to the role that grants the rights they need.

## FAQ

### What happens if I mess up and lock myself out while configuring?
1. SSH into the Jenkins master
2. sudo to jenkins (`sudo su - jenkins`)
3. Edit config.xml to replace `<useSecurity>true</useSecurity>` with `<useSecurity>false</useSecurity>` 
4. Restart Jenkins
5. You can then start over with the configuration

### Where do I see who has logged in?
SSH into the Jenkins master, and `ls -al /var/lib/jenkins/users`
