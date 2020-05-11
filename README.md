# terraform-basic-template
# Folder structure

The following files exist in the parent folder:
```text
.
├── LICENSE
├── README.md
├── backend.tf
├── cloudbuild.yaml
├── data_sources.tf
├── files
├── main.tf
├── outputs.tf
├── providers.tf
├── terraform.tfvars
├── variables.tf
└── version.tf
```

| Filename|Type|Purpose|
|---|---|---|
|backend.tf|file|Terraform backend configuration|
|cloudbuild.yaml|file|Sample Cloud Build pipeline|
|data_sources.tf|file|Terraform data source resources|
|files|folder|Location for any file content|
|main.tf|file|Specify resources to be created|
|outputs.tf|file|Specify values to output|
|providers.tf|file|Terraform providers used|
|terraform.tfvars|file|Terraform variable values|
|variables.tf|file|Terraform variable definition|
|version.tf|file|Pin terraform and provider versions|

# Notes
* Do not store authentication secrets or use credentials within the terraform code
  * Use environment variables, e.g. GOOGLE_APPLICATION CREDENTIALS or AWS_PROFILE
* Use Continuous Integration pipelines to automate testing
  * ``terraform fmt``
  * ``terraform init``
  * ``terraform plan``

# GCP Cloud Build CI
In order to automate CI with Github.com follow the steps below:
* Create a repo on Github.com
* Enable the Google Cloud Build marketplace addon
* Launch GCP console and connect the Github repo to the GCP Project
* Setup the Cloud Build trigger 

## Running Cloud Build locally
* Install ``cloud-build-local``
  * ``gcloud components-install cloud-build-local``
* Execute local cloud build
  * ``cloud-build-local --dry-run=false .``
