k3d cluster create argo
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

check:
k get all -n argocd
k get po -n argocd -w

kubectl port-forward svc/argocd-server -n argocd 8080:443&

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
3r1BQJigYenHVi7B

Use username 'admin' and the encoded password to login to the GUI console:
https://127.0.0.1:8080/


kubectl port-forward -n demo svc/ambassador 8088:80
