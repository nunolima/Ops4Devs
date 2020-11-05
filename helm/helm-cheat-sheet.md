# Helm Cheat Sheet

---

## helm version

```bash
helm version
```

## List available packages

```bash
helm search
```

## install helm chart

```bash
helm install <chart-name> <chart-location>
helm install grafana .
helm install grafana . --namespace <namespace>

helm install --generate-name .

helm install <name> <chart> [--namespace <ns>]  # Per-default you need to provide a release name
helm install -g <chart>     [--namespace <ns>]  # Helm 2 like generated release name
```

## List installed releases

```bash
helm list
helm get values <release>           # Print the values the release was installed with
```

## Upgrading releases

```bash
helm upgrade <name>
helm upgrade --wait <name>                      # Wait for pods to come up
```

## Working with plugins

```bash
helm plugin list
helm plugin install <plugin URL>
```

## delete a release

```bash
helm del <release-name>
helm del <release-name> --namespace <namespace>

[note: --purge is not required as it is handled by default]
```

## add helm repo

```bash
helm repo add stable https://kubernetes-charts.storage.googleapis.com
helm repo ls
helm fetch stable/prometheus-operator
helm install <release-name> -n <namespace> stable/prometheus-operator
```

## Creating chart packages

```bash
helm create mychart                                    # Create boilerplate
helm install mychart-0.1.0.tgz --dry-run --debug       # Test installing
```

## Helm Best Practices

See [Helm Best Practices](https://lzone.de/blog/Helm+Best+Practices)
