```bash
docker build -t mlflow-app .

docker run -dp 5001:5000 mlflow-app
```


### REPLACE PROJECT_ID WITH YOUR PROJECT ID

```bash

gcloud config set project PROJECT_ID

docker build --platform=linux/amd64 -t gcr.io/PROJECT_ID/mlflow-app:latest .


gcloud auth configure-docker
docker push gcr.io/PROJECT_ID/mlflow-app:latest
```

```bash
gcloud run deploy mlflow-server \
  --image gcr.io/PROJECT_ID/mlflow-app:latest \
  --platform managed \
  --region us-west1 \
  --allow-unauthenticated \
  --port 5000
```

