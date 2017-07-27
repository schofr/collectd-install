[ec2-user@ip-172-31-0-250 ~]$ mkdir collectd
[ec2-user@ip-172-31-0-250 ~]$ ls
collectd  rhel-6-resources.tgz
[ec2-user@ip-172-31-0-250 ~]$ tar -C /home/ec2-user/collectd -xzf rhel-6-resources.tgz 
[ec2-user@ip-172-31-0-250 ~]$ ls
collectd  rhel-6-resources.tgz
[ec2-user@ip-172-31-0-250 ~]$ cd collectd
[ec2-user@ip-172-31-0-250 collectd]$ ls
install-files.tgz  install.sh  signalfx-collectd  signalfx-collectd-plugin
[ec2-user@ip-172-31-0-250 collectd]$ sh install.sh APITOKENGOESHERE --local-resources /home/ec2-user/collectd
```


[10:00] 
Basically they need to:
1. Copy the tar file where they want to stage this
2. make a directory
3. Untar the file to the directory
4. run the install script specifying the flag (--local-resources <path to where the contents of the tar file were placed>) - no trailing /

The tar file includes all 3rd party dependencies.  I think that the only network connection required is to our ingest api.


[10:01] 
The install script creates two Yum repo configuration files that point the local rpms for collectd and the signalfx-plugin.


[10:01] 
If the local-resources path isn't specified correctly, the repo configs will be wrong and the customer will need to correct them.