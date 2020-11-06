# Ops4Devs

---

Operations for Developers

## kubectl

[kubectl site](https://kubernetes.io/docs/reference/kubectl/kubectl/)
[kubectl cheat sheet](https://v1-16.docs.kubernetes.io/docs/reference/kubectl/cheatsheet/)

### How to install kubectl

```bash
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client
```

### Define default namespace

The next command will add or update our kube config file at current context the selected namespace.

```bash
kubectl config set-context --current --namespace=default
```

### Use a shell inside a namespace

```bash
kubectl run -i -t my-shell -n default --restart=Never --rm=true --image=alpine:latest -- /bin/ash
``` 

### Generate a deployment yaml manifest

```bash
kubectl create deployment my-app --image=my-app-image:latest --dry-run=client -o yaml > deployment.yaml
``` 
