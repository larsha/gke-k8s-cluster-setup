# Setup cluster on GKE

```bash
# Create SSD StorageClass
kubectl create -f storage.yml

# Setup Tiller/Helm (make sure you have Helm installed locally)
kubectl create -f rbac-config.yml
helm init --service-account tiller

# Create Nginx ingress (if needed)
kubectl create -f kube-ingress.yml
```

### Intall cert-manager
1. Install https://github.com/jetstack/cert-manager
2. Create new Service Account `clouddns-service-account` with full access to Cloud DNS and download the key as JSON.
3. Create a secret with that service account using
`kubectl create secret -n kube-system generic clouddns-service-account --from-file=./service-account.json`
4. Remove key locally!

```bash
  # Create cert-manager
  kubectl create -f clusterissuer.yml
```
