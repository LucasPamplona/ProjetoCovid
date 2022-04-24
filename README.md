Covid_Python

Desafio do curso Engenheiro de dados Semantix

Para o projeto de Campanha nacional de vacinação de Covid-19 foi feito apenas o nível básico.
Apenas as questões 6,8 e 9 não foram feitas.


Dataset utilizado para o Nível Básico Dados: https://mobileapps.saude.gov.br/esus-vepi/files/unAFkcaNDeXajurGB7LChj8SgQYS2ptm/04bd3419b22b9cc5c6efac2c6528100d_HIST_PAINEL_COVIDBR_06jul2021.rar

Foi utilizado como ambiente de estudo o docker Big data do Instrutor Rodrigo Augusto Rebouças: https://github.com/rodrigo-reboucas/docker-bigdata


# Configurar o jar do spark para aceitar o formato parquet em tabelas Hive

curl -O https://repo1.maven.org/maven2/com/twitter/parquet-hadoop-bundle/1.6.0/parquet-hadoop-bundle-1.6.0.jar  
docker cp parquet-hadoop-bundle-1.6.0.jar jupyter-spark:/opt/spark/jars

#Executar o namenode para copiar os arquivos para o HDFS
docker exec -it namenode bash

#Subir os arquivos para o HDFS salvos no diretorio /input/covid/
hdfs dfs -put /input/covid/ /user/lucas/data/covid


# Executar o hive-server para criar a database covid

docker exec -it hive-server bash

# No hive executar o comando hive para entrar no banco de dados

hive

# Criar a database covid

create database covid;

-----

O projeto foi feito utilizando o Jupyter-notebook foi exportado o seguinte arquivo: Casos_Covid.ipynb em complemento também existe o arquivo covid_comandos_jupyter_notebook.txt, onde possui todos os comandos utilizado no jupyter-notebook

