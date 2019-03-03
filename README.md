kubectl --namespace monitoring port-forward svc/prometheus-k8s 9090

kubectl --namespace monitoring port-forward svc/grafana 3000

kubectl --namespace monitoring port-forward svc/alertmanager-main 9093



kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}')

dsahboard:
kubectl proxy
http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy