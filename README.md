# Create namespace
kubectl create namespace juice

# Deploy Juice Shop applications as two services "juiceshop-svc" and "juiceshop-svc-v2"
kubectl apply -f juiceshop.yaml

# Deploy resources for App Protect
kubectl apply -f syslog.yaml
kubectl apply -f ap-logconf.yaml
kubectl apply -f ap-dataguard-alarm-policy.yaml
kubectl apply -f waf.yaml

# Deploy VirtualServer of NGINX Ingress Controller
kubectl apply -f juiceshop-vs.yaml
