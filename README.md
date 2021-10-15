# Criando-seu-Ecossistema-de-Big-Data-na-Nuvem
O presente repositório mostra os passos tomados para a reprodução do projeto realizado no bootcamp Cognizant Cloud Data Engineer pela Digital Innovation One. Nele foi utilizado a plataforma de computação em nuvem da Amazon Web Services (AWS) para a execução de um script em python que faz a contagem de palavras de um livro utilizando configuração de um cluster EMR para processamento em paralelo de dados. A seguir é mostrado a sequência de passos para execução do projeto. O objetivo do projeto é dar uma idéia de como é possível tratar de um grande volume de dados utilizando processamento paralelo gerenciado pela própria AWS de maneira simples, mostrando um exemplo de projeto de Big Data.

## Instruções

* Acessar S3: https://s3.console.aws.amazon.com/s3/ 
  * Criar estrutura de data lake : _dio-live-datalake_
  * Criar estrutura de pastas:
    * _data_
    * _output_
    * _temp_
* Acessar EMR: https://console.aws.amazon.com/elasticmapreduce/
    * O cluster será criado pelo MrJob e não pelo console
    * Infraestrutura como código 
* Criar chave SSH
    * Acessar  Console do EC2: https://console.aws.amazon.com/ec2/ -> Key Pairs -> Create Key Pair	
    * Download .pem file
* Obter Id e chave secreta AWS para configurar MrJob
   * Profile
   * My Security Credentials: https://console.aws.amazon.com/iam/home?region={region}#/security_credentials
   * Access Keys - Create new access key
   * Fazer download - única chance de visualizar
* Ambiente linux
   * Criar ambiente virtual python: _virtualenv --python=python3.6 venv_diolive_
   * Acessar com o vs code
* Instalar vscode no Ubuntu
   *  code .
* Criar algoritmo de análise de palavras
   * dio-live-wordcount-test.py
   * map-reduce-count : contar
   * Instalar boto3: _pip install boto3_
   * Instalar mrjob: _pip install mrjob_
* Acessar S3
   * Upload de arquivo para o bucket
* Ambiente virtual python: source venv_teste/bin/activate
  * _nano ~/.mrjob.conf_
  * _python3 dio-live-wordcount-test.py -r emr s3://{your_s3_bucket_name}/data/SherlockHolmes.txt --output-dir=s3://{your_s3_bucket_name}/output/logs1 --cloud-tmp-dir=s3://{your_s3_bucket_name}/temp/_

Ao fim o arquivo pode ser baixado no próprio bucket S3 criado contendo as palavras e o número de aparições de cada palavra.
