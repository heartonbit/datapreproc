FROM jupyter/r-notebook:r-4.2.2

USER root

RUN apt-get -y update && apt-get -y install \
    software-properties-common \
    curl \
    wget \
    git \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Google Cloud SDK
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key --keyring /usr/share/keyrings/cloud.google.gpg  add - && apt-get update -y && apt-get install google-cloud-cli -y
RUN mkdir -p /.config/gcloud && chmod -R 777 /.config/gcloud

# Install python modules
RUN pip install papermill pandas numpy pyarrow dask lxml parquet-cli google-cloud-bigquery db-dtypes openpyxl

USER ${NB_UID}