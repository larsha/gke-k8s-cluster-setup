# Setup cluster on GKE

```bash
# Create SSD StorageClass
kubectl create -f storage.yml

# Setup Tiller/Helm (make sure you have Helm installed locally)
kubectl create -f rbac-config.yml
helm init --service-account tiller

# Create Nginx ingress
kubectl create -f kube-ingress.yml

# Create LE
kubectl create -f kube-lego.yml
```
