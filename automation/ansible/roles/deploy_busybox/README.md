# deploy_busybox

Deploys a busybox pod into a target OpenShift namespace.

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `deploy_busybox_namespace` | `ansible_test_monorepo` | Namespace to deploy the pod into |
| `deploy_busybox_pod_name` | `busybox` | Name of the Pod resource |

## Requirements

`kubernetes.core` collection must be available and a valid kubeconfig must be present.
