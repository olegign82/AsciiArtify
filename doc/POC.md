AsciiArtify PoC
---

Steps to deploy ArgoCD on Kubernetes (k3d):

1. Create k3d cluster argo:
```
k3d cluster create argo
```
2. Create namespace argocd:
```
kubectl create namespace argocd
```
3. Install ArgoCD using kubectl apply command:
```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
Verify state and containers:
```
k get all -n argocd
k get po -n argocd -w
```
4. Configure access to argocd-server service located inside argocd namespace using port-forward:
```
kubectl port-forward svc/argocd-server -n argocd 8080:443&
```
5. Retrieve admin user password using kubectl get secret command:
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
The password is:
```
3r1BQJigYenHVi7B
```
See short video recording below of the steps executed:
![Image](../.data/demo_argocd.gif)

6. Use username 'admin' and the encoded password to login to ArgoCD GUI console:
https://127.0.0.1:8080/

Follow the steps provided in the video below to create new application demo in the new namespace demo poiting to repository 
https://github.com/olegign82/go-demo-app.

![Image](../.data/argocd_gui.gif)



