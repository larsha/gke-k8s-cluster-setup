# Setup cluster on GKE
Including nginx ingress, let's encrypt and ssd storage class for dynamic provision of PersistentVolumes.

```bash
# Create SSD StorageClass
kubectl create -f storage.yml

# Create Let's Encrypt automation
kubectl create -f kube-lego.yml

# Create Nginx ingress
kubectl create -f kube-ingress.yml
```
