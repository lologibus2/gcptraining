# Objective

Now, your will train your first model on GCP.
The goal is to build a very simple model for the taxi fare prediction problem and submit a training job to AI platform  

We provide you with the code to run for this simple model
Steps of TaxiFareModel/trainer.py :
- get sample of training data from Google Cloud Storage Bucket
- train simple model
- upload model to Google Cloud Storage

## Install Requirements

Make sure you have done following steps:
- created a GCP account
- fetch Service Account key and added them to your .zshrc (or .bash_profile) To check run :
```bash
echo $GOOGLE_APPLICATION_CREDENTIALS
```
Check that it return a path to your credentials  
- Enable the AI Platform Training & Prediction and Compute Engine APIs on [GCP console](https://console.cloud.google.com/flows/enableapi?apiid=ml.googleapis.com,compute_component&_ga=2.269215094.662509797.1580849510-2071889129.1567861089&_gac=1.154971594.1580849512.CjwKCAiAyeTxBRBvEiwAuM8dnbZ6uMwizbZW44J2mBCX6ncEjwjwpgF8S8QsvhYAXLkJ8awDnIRTNRoCJ_0QAvD_BwE)

## Check that the code runs locally

Update variables `BUCKET_NAME` `PATH_INSIDE_BUCKET` inside `TaxiFareModel/trainer.py`

Launch Training locally

```bash
nake run_locally
```

Check that :
- model.joblib file was stored locally
- You can now check on Google Cloud Storage that you model has been uploaded  

## Submit Training to GCP

Inspect Makefile
Ensure you have correct python (3.7) and runtime (1.15) versions, more info on latest runtimes on [GCP Documentation](https://cloud.google.com/ai-platform/training/docs/runtime-version-list?hl=en)

```bash
PYTHON_VERSION=3.7
RUNTIME_VERSION=1.15
```

Then run :
```bash
nake gcp_submit_training
```
Check that :
- You can now check on Google Cloud Storage that you model has been uploaded

## Train model on GCP

Visit [https://cloud.google.com/sdk/gcloud/reference/ai-platform/jobs/submit/training](https://cloud.google.com/sdk/gcloud/reference/ai-platform/jobs/submit/training)

Inspect Makefile, complete environement variables and run
```bash
make gcp_submit_training
```
# gcptraining
