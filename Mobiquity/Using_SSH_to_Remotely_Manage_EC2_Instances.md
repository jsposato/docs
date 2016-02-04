# Amazon Key
Make sure you have the Amazon key in your ~/.ssh folder

Make sure the permissions on the key file are 600 (chmod 600 mobci_jsposato.pem)

# How to SSH in
The command will look something like this:

```
ssh -i ~/.ssh/mobci_jsposato.pem centos@[JENKINS_MASTER_IP]
```

