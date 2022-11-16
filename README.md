# namespace-event-exporter

## overview
This Helm Chart installs [Kubernetes Event Exporter](https://github.com/resmoio/kubernetes-event-exporter)
and watch for events in the installed namespace.

Look at the [Readme](https://github.com/resmoio/kubernetes-event-exporter/blob/master/README.md) for route
and receive the events to various systems. The simplest workflow is to route the events to stdout of
the container

```yaml
routes:
  - match:
      - receiver: dump
receivers:
  - name: dump
    stdout: { }
```

## installation

via Helm Chart Repo (required helm 3.10+):

```bash
helm -n <namespace> upgrade -i <app_name> -f values.yaml --version 1.0.0 oci://mtr.devops.telekom.de/caas/charts/namespace-event-exporter
```
