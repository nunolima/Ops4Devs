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

