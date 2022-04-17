# Installing Rancher

## What is rancher?
Rancher is a complete software stack for teams adopting containers. It addresses the operational and security challenges of managing multiple Kubernetes clusters, while providing DevOps teams with integrated tools for running containerized workloads. Yes marketing sluring, but simply put helps remove all the yaml config requried for kubernities management. 

## How to install
The following this tutorial (Link)[https://phoenixnap.com/kb/install-rancher-on-ubuntu]

However if you struggle in creating a host it's propably because of the localhosts are resolved, some linux systems use local caching name servers. This means that the configuration nameserver in `/etc/resolv.conf` is pointing to address in loopback range (`127.0.0.0/8`). This is typically fine if the network is runnign in`host` mode. This involves :

* Modifying the contents of /etc/resolv.conf to point to correct nameservers.
```sh
# Remove the original reference and add the correct nameservers
sudo rm /etc/resolv.conf
sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf
```
If /run/systemd/resolve/resolv.conf is not present on the system, you can create your own /etc/resolv.conf as shown below:
```
nameserver 8.8.8.8
nameserver 8.8.4.4
nameserver 192.168.X.X
```
just replace X.X with your local host IP. 
