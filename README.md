# kurento-install

https://doc-kurento.readthedocs.io/en/stable/user/installation.html#local-installation

https://doc-kurento.readthedocs.io/en/stable/user/installation.html#check-your-installation


https://github.com/nhancv/ot-kurento-node-webrtc

Local Installation

With this method, you will install KMS from the native Ubuntu package repositories made available by the Kurento project.

KMS has explicit support KMS has explicit support for two Long-Term Support (LTS) versions of Ubuntu: Ubuntu 16.04 (Xenial) and Ubuntu 18.04 (Bionic) (64-bits only). To install KMS, open a terminal and follow these steps:

    Make sure that GnuPG is installed.

    sudo apt-get update \
      && sudo apt-get install --no-install-recommends --yes \
         gnupg

    Define what version of Ubuntu is installed in your system.

    Run only one of these lines:

    # Run ONLY ONE of these lines:
    DISTRO="xenial"  # KMS for Ubuntu 16.04 (Xenial)
    DISTRO="bionic"  # KMS for Ubuntu 18.04 (Bionic)

    Add the Kurento repository to your system configuration.

    Run these two commands in the same terminal you used in the previous step:

    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5AFA7A83

    sudo tee "/etc/apt/sources.list.d/kurento.list" >/dev/null <<EOF
    # Kurento Media Server - Release packages
    deb [arch=amd64] http://ubuntu.openvidu.io/6.10.0 $DISTRO kms6
    EOF

    Install KMS:

    sudo apt-get update \
      && sudo apt-get install --yes kurento-media-server

This will install the KMS release version that was specified in the previous commands.

The server includes service files which integrate with the Ubuntu init system, so you can use the following commands to start and stop it:

sudo service kurento-media-server start
sudo service kurento-media-server stop

Log messages from KMS will be available in /var/log/kurento-media-server/. For more details about KMS logs, check Debug Logging.


https://doc-kurento.readthedocs.io/en/stable/tutorials/js/tutorial-helloworld.html

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm install -g bower

sudo npm install http-server -g

git clone https://github.com/Kurento/kurento-tutorial-js.git
cd kurento-tutorial-js/kurento-hello-world
git checkout 6.10.0
sudo bower install --allow-root
http-server -p 8443 -S -C keys/server.crt -K keys/server.key

```
The server includes service files which integrate with the Ubuntu init system, so you can use the following commands to start and stop it:
```
sudo service kurento-media-server start
sudo service kurento-media-server stop
```


Check your installation

To verify that KMS is up and running, use this command and look for the kurento-media-server process:
```
ps -ef | grep kurento-media-server
```
> nobody  1270  1  0 08:52 ?  00:01:00  /usr/bin/kurento-media-server

Unless configured otherwise, KMS will open the port 8888 to receive requests and send responses by means of the Kurento Protocol. Use this command to verify that this port is listening for incoming packets:
```
sudo netstat -tupan | grep kurento
```
> tcp6  0  0 :::8888  :::*  LISTEN  1270/kurento-media-server



# Writing Kurento Modules
https://doc-kurento.readthedocs.io/en/stable/features/kurento_modules.html

https://doc-kurento.readthedocs.io/en/stable/user/writing_modules.html

https://meetrix.io/blog/webrtc/kurento/creating-an-opencv-filter-for-kurento-media-server.html
# help line
https://doc-kurento.readthedocs.io/en/6.9.0/features/security.html
