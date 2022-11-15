# Flux

```
Examples:
  # Check prerequisites
  flux check --pre

  # Install the latest version of Flux
  flux install

  # Create a source for a public Git repository
  flux create source git webapp-latest \
    --url=https://github.com/stefanprodan/podinfo \
    --branch=master \
    --interval=3m

  # List GitRepository sources and their status
  flux get sources git

  # Trigger a GitRepository source reconciliation
  flux reconcile source git flux-system

  # Export GitRepository sources in YAML format
  flux export source git --all > sources.yaml

  # Create a Kustomization for deploying a series of microservices
  flux create kustomization webapp-dev \
    --source=webapp-latest \
    --path="./deploy/webapp/" \
    --prune=true \
    --interval=5m \
    --health-check="Deployment/backend.webapp" \
    --health-check="Deployment/frontend.webapp" \
    --health-check-timeout=2m

  # Trigger a git sync of the Kustomization's source and apply changes
  flux reconcile kustomization webapp-dev --with-source

  # Suspend a Kustomization reconciliation
  flux suspend kustomization webapp-dev

  # Export Kustomizations in YAML format
  flux export kustomization --all > kustomizations.yaml

  # Resume a Kustomization reconciliation
  flux resume kustomization webapp-dev

  # Delete a Kustomization
  flux delete kustomization webapp-dev

  # Delete a GitRepository source
  flux delete source git webapp-latest

  # Uninstall Flux and delete CRDs
  flux uninstall

Available Commands:
  bootstrap   Bootstrap toolkit components
  build       Build a flux resource
  check       Check requirements and installation
  completion  Generates completion scripts for various shells
  create      Create or update sources and resources
  delete      Delete sources and resources
  diff        Diff a flux resource
  export      Export resources in YAML format
  get         Get the resources and their status
  help        Help about any command
  install     Install or upgrade Flux
  list        List artifacts
  logs        Display formatted logs for Flux components
  pull        Pull artifacts
  push        Push artifacts
  reconcile   Reconcile sources and resources
  resume      Resume suspended resources
  suspend     Suspend resources
  tag         Tag artifacts
  trace       Trace in-cluster objects throughout the GitOps delivery pipeline
  tree        Print the resources reconciled by Flux
  uninstall   Uninstall Flux and its custom resource definitions
  version     Print the client and server-side components version information.

Flags:
      --as string                      Username to impersonate for the operation. User could be a regular user or a service account in a namespace.
      --as-group stringArray           Group to impersonate for the operation, this flag can be repeated to specify multiple groups.
      --as-uid string                  UID to impersonate for the operation.
      --cache-dir string               Default cache directory (default "c:\\users\\weimann\\.kube\\cache")
      --certificate-authority string   Path to a cert file for the certificate authority
      --client-certificate string      Path to a client certificate file for TLS
      --client-key string              Path to a client key file for TLS
      --cluster string                 The name of the kubeconfig cluster to use
      --context string                 The name of the kubeconfig context to use
  -h, --help                           help for flux
      --insecure-skip-tls-verify       If true, the server's certificate will not be checked for validity. This will make your HTTPS connections insecure
      --kube-api-burst int             The maximum burst queries-per-second of requests sent to the Kubernetes API. (default 100)
      --kube-api-qps float32           The maximum queries-per-second of requests sent to the Kubernetes API. (default 50)
      --kubeconfig string              Path to the kubeconfig file to use for CLI requests.
  -n, --namespace string               If present, the namespace scope for this CLI request (default "flux-system")
      --server string                  The address and port of the Kubernetes API server
      --timeout duration               timeout for this operation (default 5m0s)
      --tls-server-name string         Server name to use for server certificate validation. If it is not provided, the hostname used to contact the server is used
      --token string                   Bearer token for authentication to the API server
      --user string                    The name of the kubeconfig user to use
      --verbose                        print generated objects
  -v, --version                        version for flux

Use "flux [command] --help" for more information about a command.
```