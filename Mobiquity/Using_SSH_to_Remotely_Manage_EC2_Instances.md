# SSH Into FIRE Jenkins Master and Android Build Slave

## Amazon Key
Make sure you have the Amazon key in your ~/.ssh folder

Make sure the permissions on the key file are 600 (chmod 600 mobci-jsposato.pem)

## How to SSH in to Jenkins master
The command will look something like this:

```
ssh -i ~/.ssh/mobci-jsposato.pem centos@[JENKINS_MASTER_IP]
```

## To run commands with elevated privileges you must first change to the root user
```
sudo su
```

## How to tunnel from Jenkins master to your Android Slave
Follow the previous step to login to Jenkins master

Then run

```
sudo su - jenkins
ssh -i ~/.ssh/dhelmick-testing.pem [ANDROID_SLAVE_IP]
```

## How to SSH into the iOS build slave
```
ssh jenkins_slave@[OSX_NODE_IP]
```

If you don't know the password, ask. 

## How to VNC into the iOS build slave

From a Finder window, press CMD+K

In the server address field, put:
```
vnc://[OSX_NODE_IP]
```

Account name is `administrator`

If you don't know the password, ask.

You are now remotely viewing the iOS build node's desktop

