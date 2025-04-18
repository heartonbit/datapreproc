FROM rapidsai/notebooks:24.08-cuda12.2-py3.11

# Install Google Cloud SDK
RUN echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" \
    | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list \
    && curl https://packages.cloud.google.com/apt/doc/apt-key.gpg \
    | apt-key --keyring /usr/share/keyrings/cloud.google.gpg  add - \
    && apt-get update -y \
    && apt-get install google-cloud-cli -y \
    && mkdir -p /.config/gcloud \
    && chmod -R 777 /.config/gcloud

RUN source activate rapids && \
    pip install papermill \
	pandas \
	numpy \
	pyarrow \
	dask \
	lxml \
	parquet-cli \
	google-cloud-bigquery \
	db-dtypes \
	openpyxl \
	obonet \
	networkx \
	xmltodict \
	cmapPy 
