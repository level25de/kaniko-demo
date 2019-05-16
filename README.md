# Kaniko demo

Slides: http://bit.ly/kaniko-slides

All commands require a running kubernetes cluster, kubectl configuration and the gcloud sdk
to be initialized.

Kubernetes steps:
```
kubectl apply -k k8s/setup/
kubectl apply -k k8s/run/

echo http://$(kubectl get svc flask -o jsonpath="{.status.loadBalancer.ingress[0].hostname}")

kubectl delete -k k8s/setup/
kubectl delete -k k8s/run/
```

Google Cloud Build:
```
gcloud builds submit --config gcb/build.yaml
```
