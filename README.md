# fast-api-demo-helm-chart

A Helm chart for deploying a FastAPI demo. You can find an example in
[this repo](https://github.com/luismesalas/fast-api-demo).

## TODO include some doc about values.yaml parameters config

## Quick help about helm commands

```shell
# This downloads required external charts, postgresql in this particular case
helm dependency update

# This creates a new k8s namespace (only if you didn't create it yet)
kubectl create namespace fast-api-demo-ns

# And this deploy the chart for the first time
helm install fast-api-demo --namespace fast-api-demo-ns -f values.yaml .

# With this command you can upgrade it
helm upgrade fast-api-demo --namespace fast-api-demo-ns -f values.yaml .

# This will show you all revisions of your deployments
helm history fast-api-demo --namespace fast-api-demo-ns

# This allows you to switch to a previous revision (1 in this example)
helm rollback fast-api-demo --namespace fast-api-demo-ns 1

# And with this other you can delete it
helm delete fast-api-demo --namespace fast-api-demo-ns
```