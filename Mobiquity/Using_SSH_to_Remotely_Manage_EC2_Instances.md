# SSH Into FIRE Jenkins Master and Android Build Slave

## Amazon Key
Make sure you have the Amazon key in your ~/.ssh folder

Make sure the permissions on the key file are 600 (chmod 600 mobci-jsposato.pem)

## How to SSH in to Jenkins master
The command will look something like this:

```
ssh -i ~/.ssh/mobci-jsposato.pem centos@[JENKINS_MASTER_IP]
```

## How to tunnel from Jenkins master to your Android Slave
Follow the previous step to login to Jenkins master

Then run

```
sudo su - jenkins
ssh -i ~/.ssh/dhelmick-testing.pem [ANDROID_SLAVE_IP]
```
