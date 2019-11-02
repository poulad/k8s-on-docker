# Contour Ingress

Contour is a Kubernetes ingress controller.

```sh
kubectl apply -f "1.ingress/contour-v1.0.yaml"
```

Try a test web server with Nginx.

```sh
kubectl apply -f "1.ingress/test-server.nginx.yaml"
```

Hit http://localhost after a few seconds to see the local ingress in action.

[Contour]: https://github.com/projectcontour/contour
