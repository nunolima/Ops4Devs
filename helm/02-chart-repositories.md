# Helm Chart Repositories

[<< Back](./README.md)

## Add and Update a Chart Repository

```bash
# to add the stable chart repo
helm repo add stable https://charts.helm.sh/stable

# to list all added chart repos
helm repo list

# to get the latest list of charts
helm repo update
```

## List a Repository Charts

```bash
# to list ALL charts
helm search repo

# to list ALL charts from the "stable" repo
helm search repo stable/

# to list all charts with word "redis" in is NAME or DESCRIPTION
helm search repo redis
```

## Pull (to localhost) a Chart from the a Repository

```bash
# to download/pull (the "redis" .tgz) Chart from stable repo
helm pull stable/redis

# to pull and unzip it
helm pull stable/redis --untar

# to pull and unzip it to a folder
helm pull stable/redis --untar --untardir my-local-charts
```

Example of downloading some Charts to a local directory and creating an index file

```bash
mkdir ./local-charts
helm pull stable/redis-ha -d local-charts/
helm pull stable/cerebro -d local-charts/
helm pull stable/couchdb -d local-charts/
ls local-charts/    # cerebro-1.9.3.tgz  couchdb-2.3.0.tgz  redis-ha-4.4.4.tgz

# Read the current directory and generate an 'index.yaml' file based on the charts found.
helm repo index local-charts/
```
