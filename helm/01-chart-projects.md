# Helm Charts

[<< Back](./README.md)

## Chart Projects

A Helm Chart groups all YAML definitions required to deploy a working version of our developed projects including its metadata, default values and after deployment instruction.

Charts can be converted to a package (tar.gz file) and shared directly or using a private or public Helm Repository.

### Helm Chart sample 

Sample project diagram

![3 tier project](./imgs/k8s-helm-3-tier.png)

```bash
# to create a Chart project directory and basic structure
export PROJECT=myapp
helm create $PROJECT
```

The above command will create a directory with the following structure.

```ASCII
myapp
├── charts
├── Chart.yaml
├── templates
│   ├── deployment.yaml
│   ├── _helpers.tpl
│   ├── hpa.yaml
│   ├── ingress.yaml
│   ├── NOTES.txt
│   ├── serviceaccount.yaml
│   ├── service.yaml
│   └── tests
│       └── test-connection.yaml
└── values.yaml
```

#### Chart.yaml

This file stores the metadata of our project.
Here we can define the project name and description. 
The minimum required cluster and helm versions and the current Chart version so we can then manage helm upgrades or rollbacks.

#### *templates/* directory

In *templates/* folder we place YAML definitions for all Kubernetes objects we need for our project.
The "helm create" command gived us same examples:

- deployment.yaml
- hpa.yaml
- ingress.yaml
- serviceaccount.yaml
- service.yaml

We can replace, delete or create some other files.

Commands like, "helm install" or "helm update" will trigger Helm template rendering engine. 

It uses the [*GoLang "template" package*](https://golang.org/pkg/text/template/) that searchs for strings delimited by "{{" and "}}". This are called "Actions" and they can be "data evaluations" or "control structures".

#### values.yaml

lalala
