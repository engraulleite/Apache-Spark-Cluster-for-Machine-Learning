# Inicializar o cluster
docker-compose up -d --scale spark-worker=3

# Visualizar os logs
docker-compose logs

# Executar o pipeline:
docker exec raul-spark-master spark-submit --master yarn --deploy-mode cluster ./apps/pipeline_mk.py

# Derrubar o cluster
docker-compose down --volumes --remove-orphans