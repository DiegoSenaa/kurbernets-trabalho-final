# kurbernets-trabalho-final

Rodando o projeto

1 - Esta logado na gcloud

2- Adicionar a ENV_VARIABLE export PROJECT_ID={id do projeto na gcp}

3- Criar o cluster gke ``gcloud container clusters create labgke --num-nodes=2``

4- Criar o name space ``kubectl create namespace labgke``

5- Fazer o build da imagem ``docker build -t gcr.io/${PROJECT_ID}/myfirstapp:2.0 .``

6- Subir a imagem para o registry ``gcloud auth configure-docker && docker build -t gcr.io/${PROJECT_ID}/myfirstapp:2.0 .``

7- Criar o pod `` kubectl apply -f myfirstapp-deployment.yaml ``

8- Criar o service para expor `` kubectl apply -f myfirstapp-service.yaml ``

9 - Pegar o IP gerado para acessar o app ``kubectl get service myfirstapp-lb-service``

10- Deletar a estrutura criada `` kubectl delete service myfirstapp-lb-service && gcloud container clusters delete labgke && gcloud container images delete gcr.io/$PROJECT_ID/myfirstapp:2.0 ``
