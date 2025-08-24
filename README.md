# purge-k8s

## purge docker
sudo apt-get purge -y docker-engine docker docker.io docker-ce docker-ce-cli docker-buildx-plugin docker-compose-plugin  
sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce docker-buildx-plugin docker-compose-plugin  

sudo rm -rf /var/lib/docker /etc/docker  
sudo rm /etc/apparmor.d/docker  
sudo groupdel docker  
sudo rm -rf /var/run/docker.sock  

sudo rm -rf /usr/local/bin/docker-compose  
sudo rm -rf /etc/docker  
sudo rm -rf ~/.docker  

## purge containerd
sudo systemctl stop docker  
sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y  
sudo rm -rf /var/lib/docker  
sudo rm -rf /var/lib/containerd  
sudo rm -rf /etc/docker  
sudo rm -rf /var/run/docker.sock  
sudo apt-get remove docker docker-engine docker.io containerd runc  
sudo apt-get autoremove --purge -y  


## purge k8s
kubeadm reset
sudo apt-get purge -y kubeadm kubectl kubelet kubernetes-cni kube*   
sudo apt-get -y autoremove  
sudo rm -rf ~/.kube
