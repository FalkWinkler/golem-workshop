# 5. Production-grade Deployments

* Deploy application
```
kubectl apply -f 05-production-grade-deployments/web-application/deployment/
```
* Check pods and figure out why pods are pending
```
kubectl get pods
kubectl describe pods
```
* Label Nodes
```
kubectl get nodes
kubectl label nodes nodename storagetype=network 
```
* See that pods are schedules
```
kubectl get pods
```
* Create autoscaler
```
kubectl autoscale deployment web-application --min=1 --max=6 --cpu-percent=2
kubectl get horizontalpodautoscaler
kubectl describe horizontalpodautoscalers web-application
kubectl top pods
```
* Watch pods and create traffic
```
watch kubectl get pods
ab -c 100 -n 1000 https://IP_ADDRESS/
```