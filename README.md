# BigQuery & dbt Warehouse

## Setup 
```shell
cd projectDir
pip install virtualenv
#create virtual env
python -m venv dbt-env
#activate env
source dbt-env/Scripts/activate
#install dbt
pip install dbt-bigquery
# start project
dbt init northwind
# for authentication method select oauth
```
### Local OAuth gcloud setup
To connect to BigQuery using the `oauth` method, follow these steps:

1. Make sure the `gcloud` command is [installed on your computer](https://cloud.google.com/sdk/downloads)
2. Activate the application-default account with
```shell
gcloud auth application-default login \
  --scopes=https://www.googleapis.com/auth/bigquery,\
https://www.googleapis.com/auth/drive.readonly,\
https://www.googleapis.com/auth/iam.test
```
A browser window should open, and you should be prompted to log into your Google account. Once you've done that, dbt will use your OAuth'd credentials to connect to BigQuery!