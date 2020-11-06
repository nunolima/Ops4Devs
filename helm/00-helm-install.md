# Helm install

[<< Back](./README.md)

## Install

We can find the latest version of the helm binary tool [here](https://github.com/helm/helm/releases/latest).

Example steps:

```bash
wget -LqO helm.tar.gz https://get.helm.sh/helm-v3.4.0-linux-amd64.tar.gz
tar -xzvf helm.tar.gz
chmod +x linux-amd64/helm
sudo mv linux-amd64/helm /usr/local/bin/helm

# add helm completion to bash
echo "source <(helm completion bash)" >> ~/.bashrc
source ~/.bashrc

# helm version
helm version
```

## Initialize a Helm Chart Repository

```bash
# to add the stable chart repo
helm repo add stable https://charts.helm.sh/stable

# to list all added chart repos
helm repo list

# to get the latest list of charts
helm repo update
```
