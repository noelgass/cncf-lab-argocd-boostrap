# cncf-lab-argocd-boostrap

## Helm Chart

### Templating

```bash
cd path/to/dir

helm template <chart-name> <chart> -f <values-file>

# Examples
helm template kube-prometheus ./helm/infrastructure/kube-prometheus --include-crds --output-dir ./templates
helm template kafka ./helm/workloads/kafka  --include-crds --output-dir ./templates
helm template kafka-ui ./helm/workloads/kafka-ui --include-crds --output-dir ./templates

helm template podinfo ./helm/workloads/podinfo  --include-crds --output-dir ./templates
```

### Helm Files

**Download and Extract**:

```bash
helm pull <chart-name> --untar --untardir helm/<app-of-apps>

# Example
helm pull bitnami/kube-prometheus --destination . --untar --untardir helm/infrastructure
helm pull oci://ghcr.io/stefanprodan/charts/podinfo --destination . --untar --untardir helm/workloads
helm pull https://provectus.github.io/kafka-ui-charts --destination . --untar --untardir helm/workloads
```

**Download Helm Chart**:

```bash
helm pull <chart-name>

# Example
helm pull bitnami/kube-prometheus
```

**Extract .tgz**:

```bash
tar -zxvf <chart-name>.tgz -C helm/<app-of-apps>/<chart-name>
```

### Download

Manual download from [kafka-ui-chart](https://github.com/provectus/kafka-ui-charts), because helm pull did not work

### Questions

- gitops/infrastructure/templates/kube-prometheus.yaml: app path is not a directory
How to achieve an app for kube prometheus without this boiler plate folder structure?
- GTK Prometheus (Namespaces)
- kube-prometheus; too fast (sync-waves?)
- namespace creation does not work, why?
- handling projects, namespaces, permissions

## Target

- Playground
- PoC
- Knowledge building