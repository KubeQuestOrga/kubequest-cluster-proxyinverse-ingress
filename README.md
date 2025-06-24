# KubeQuest - Proxy Inverse / Ingress è Cluster K3s

## À quoi sert un proxy inverse / Ingress Controller dans Kubernetes ❓
Dans un cluster Kubernetes (ou K3S), les services s'exécutent dans des pods isolés, souvent sans exposition directe à Internet.
Pour permettre l’accès aux applications depuis l’extérieur (navigateur web, API, etc.), on utilise un proxy inverse, plus précisément un Ingress Controller.

🔁 Rôle principal de l’Ingress :
Router les requêtes HTTP/HTTPS/TCP/UDP entrantes vers les bons services Kubernetes

Gérer les noms de domaines (DNS) associés à tes services

Supporter des règles avancées comme :

le SSL/TLS (HTTPS),

les redirections,

les authentifications, ou encore

le rate-limiting

🎯 Dans ce setup, nous utilisons NGINX Ingress Controller, un des contrôleurs les plus populaires et maintenus par la communauté Kubernetes.

## ⚙️ Setup Environment
1. Connect to the NODE MASTER in Cluster K3S.
2. Install HELM : https://helm.sh/docs/intro/install/
3. Use repo INGRESS-NGINX HELM : https://artifacthub.io/packages/helm/ingress-nginx/ingress-nginx
4. Run command add repo INGRESS-NGINX and install :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
sudo helm repo update
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace --version 4.12.3 --values values.yaml
```

<br /><br /><br /><br />


## 🚀 Update chart INGRESS-NGINX HELM for values.yaml
1. Connect to the NODE MASTER in Cluster K3S.
2. Run command :
```bash
sudo chmod 644 /etc/rancher/k3s/k3s.yaml
sudo KUBECONFIG=/etc/rancher/k3s/k3s.yaml helm upgrade nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --values values.yaml
```
