CentOS 7 offline installer

git clone the repo and cd to this directory.

sh install.sh <SFX_API_TOKEN> --local-resources <FULL_PATH_TO_THIS_DIR>

FULL_PATH_TO_THIS_DIR has no trailing /
e.g. /home/ec2user/centos7

The install script creates two Yum repo configuration files that point the local rpms for collectd and the signalfx-plugin.
Other plugins can be installed as normal if they are in this package. 
e.g. yum install collectd-java
