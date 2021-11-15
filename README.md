# msssql-backup

# repo has the following under /backup
```
1 - mssql-backup manifest
2 - mssql-backup-secret manifest
3 - mssql-backup-configmap manifest
4 - mssql-backup-storage manifest
```
# ArcoCD app under /app
```
1 - mssql-backup-app.yaml manifest
```
# install ArgoCD
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
# get ArgoCD admin password
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```
# open ArgoCD UI and login
```
addmin/PASSWORD
```
# create ArgoCD application
```
kubectl apply -f https://raw.githubusercontent.com/wael2000/msssql-backup/main/app/mssql-backup-app.yaml -n argocd
```
