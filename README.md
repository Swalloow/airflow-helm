# airflow-helm

```
# setup, create secrets
kubectl create secret ...
kubectl apply -f settings/

# install
helm install stable/airflow \
--version 7.1.1 \
--namespace airflow \
--name airflow \
-f ./values.yaml

# update
helm status airflow
helm upgrade --namespace airflow airflow stable/airflow -f ./values.yaml

# airflow cli
kubectl exec \
  -it \
  --namespace airflow \
  --container airflow-scheduler \
  Deployment/airflow-scheduler \
  /bin/bash

# remove
helm del --purge airflow
```
