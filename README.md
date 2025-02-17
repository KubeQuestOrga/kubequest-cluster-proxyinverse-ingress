# Flapi - Cluster K3s - Proxy Inverse

## ⚙️ Setup Environment
1. Connect to the NODE MASTER in Cluster K3S.
2. Install HELM : https://helm.sh/docs/intro/install/
3. Use repo INGRESS-NGINX HELM : https://artifacthub.io/packages/helm/ingress-nginx/ingress-nginx
4. Run command add repo INGRESS-NGINX and install :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
sudo helm repo update
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace --version 4.12.0-beta.0 --values values.yaml
```

<br /><br /><br /><br />


## 🚀 Update chart INGRESS-NGINX HELM for values.yaml
1. Connect to the NODE MASTER in Cluster K3S.
2. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm upgrade nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --values values.yaml
```
