### Installing Kubeadmin 
##### NOTE:
- makes sure you have install container runtime ( Kubeadnin will automatically detect it)
- docker needed to run using systemd cgroup ( can change using --exec-opt native.cgroupdriver=systemd in start up script)

## Instructions

- Update the apt package index and install packages needed to use the Kubernetes apt repository:
```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
```
- Download the Google Cloud public signing key:
```
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
```
- add the Kubernetes apt repository:
```
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```
- Update apt package index, install kubelet, kubeadm and kubectl, and pin their version
```
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl

```


