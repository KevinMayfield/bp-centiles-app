# Deploy #

From a console in the project directory, execute:

```
npm install
npm run serve
```

```
docker build -t thorlogic/bpcentile .

docker push thorlogic/bpcentile
```


From https://cloud.google.com/cloud-build/docs/quickstart-docker

gcloud builds submit --tag gcr.io/clear-shadow-234308/bp-image .

As above but using config file

gcloud builds submit --config cloudbuild.yaml .



Now deploy 

https://cloud.google.com/kubernetes-engine/docs/tutorials/hello-app

kubectl run sof-web1 --image=gcr.io/clear-shadow-234308/bp-image --port 8001

kubectl get pods

kubectl expose deployment sof-web1 --type=LoadBalancer --port 80 --target-port 8001
