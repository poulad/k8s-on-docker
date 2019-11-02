# Kubernetes Dashboard

[Dashboard] is a web-based Kubernetes user interface.

```sh
kubectl apply -f "2.dashboard/k8s-dashboard.yaml"
```

Create an admin user service account and use its Bearer token to access the Dashboard.

```sh
kubectl apply -f "2.dashboard/k8s-dashboard.sa.yaml"

secret_name=$(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
# Use this bearer token to access the Dashboard:
kubectl describe -n kubernetes-dashboard secret $secret_name
```

Run Kube proxy server and navigate to [your local dashboard].

```sh
kubectl proxy
```

[Dashboard]: https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/
[your local dashboard]: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/
