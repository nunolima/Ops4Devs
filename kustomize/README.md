# Ops4Devs

---

Operations for Developers

## Kustomize - Kubernetes native configuration management

[Kustomize site](https://kustomize.io/)

Kustomize introduces a template-free way to customize application configuration that simplifies the use of off-the-shelf applications.
To built we must use: kubectl apply -k .

### Howto install

```bash
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
sudo mv kustomize /usr/bin/kustomize

kustomize --help

## Add kustumize completion to bash
echo "source <(kustomize completion bash)" >> ~/.bashrc
source ~/.bashrc
```
### 
