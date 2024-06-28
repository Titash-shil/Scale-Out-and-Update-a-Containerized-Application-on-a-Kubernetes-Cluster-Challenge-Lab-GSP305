# Scale Out and Update a Containerized Application on a Kubernetes Cluster: Challenge Lab || [GSP305](https://www.cloudskillsboost.google/focuses/1739?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell
```
export ZONE=
```
```
gsutil cp gs://sureskills-ql/challenge-labs/ch05-k8s-scale-and-update/echo-web-v2.tar.gz .
tar xvzf echo-web-v2.tar.gz
gcloud builds submit --tag gcr.io/$DEVSHELL_PROJECT_ID/echo-app:v2 .
gcloud container clusters get-credentials echo-cluster --zone $ZONE
kubectl create deployment echo-web --image=gcr.io/qwiklabs-resources/echo-app:v1
kubectl expose deployment echo-web --type=LoadBalancer --port 80 --target-port 8000
kubectl patch deployment echo-web -p '{"spec": {"template": {"spec": {"containers": [{"name": "echo-app", "image": "gcr.io/qwiklabs-resources/echo-app:v2"}]}}}}'
kubectl scale deploy echo-web --replicas=2
```

# Congratulations ..!! You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
