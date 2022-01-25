# evms-analysis
Notebooks for use in understanding EVMS, as well as a home for the PySpark Jobs that process and unify the data. 



gcloud dataproc clusters create cluster-evms-analysis --scopes cloud-platform --enable-component-gateway --bucket vta-sandbox --region us-east4 --zone us-east4-a --single-node --master-machine-type n1-standard-4 --master-boot-disk-size 500 --image-version 2.0-debian10 --properties dataproc:pip.packages=jupyter_enterprise_gateway==2.5.2,spark:spark.jars.packages=io.delta:delta-core_2.12:1.0.0 --optional-components JUPYTER --max-idle 7200s --project evms-analysis --initialization-actions gs://vta-sandbox/jupyter-enterprise-gateway.sh

then make an ssh connection to the master and start jupyter_enterprise_gateway. later on, we will want to make this an initialization action that runs only on the master node.
jupyter enterprisegateway --ip=0.0.0.0 --port_retries=0


