FROM rapidsai/rapidsai:cuda11.5-runtime-ubuntu20.04-py3.10

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
	git+https://github.com/minkyushim/neo4jtools.git \
	llama-index-llms-openai \
	llama-index-graph-stores-neo4j \
	llama-index-embeddings-openai \
	llama-index-agent-openai \
	llama-index-tools-neo4j \
	neo4j
