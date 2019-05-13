# kurento-install

https://doc-kurento.readthedocs.io/en/stable/user/installation.html#local-installation

https://doc-kurento.readthedocs.io/en/stable/user/installation.html#check-your-installation


https://github.com/nhancv/ot-kurento-node-webrtc

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
