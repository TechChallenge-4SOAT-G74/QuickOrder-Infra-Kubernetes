# Quick Order - Tech Challenge FIAP

Projeto do Tech Challenge da FIAP - Fase 3

**INTEGRANTES DO GRUPO 74**

* Moisés Barboza de Figueiredo Junior
moises.figueiredo@gmail.com

* Gabriela da Silva Lopes
gabrieladslopes@gmail.com

* Francisco Tadeu da Silva e Souza
fsouza.thadeu@gmail.com

<br />

<br />

## Pré-Requisitos

Antes de executar este projeto, os seguintes itens deverão estar instalados no computador:

* Docker
* Kubernetes


## Instalação pelo Kubernetes

<br />

**ARQUITETURA UTILIZADA**

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/51400a14-7ee7-4b62-a4e8-475b3ebb44fb)


<br />

Passo a passo:

* Abrir alguma interface de linha de comando como, por exemplo, o **PowerShell** e digitar o comando `kubectl config get-contexts`. O resultado deverá ser conforme abaixo, com o contexto do **docker-desktop** selecionado:
  
<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/ce7f5145-2ae7-44a0-82d5-fecf3c593589)


* Caso o contexto do **docker-desktop** não esteja selecionado, selecionar o mesmo através do comando `kubectl config set-context docker-desktop`
* Executar o comando `kubectl get all` para garantir que o cluster esteja limpo e assim prevenir que ocorram conflitos de portas nos passos posteriores. O resultado deverá ser esse:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/01637947-6284-4dd3-a148-d1cc039603f4)


<br />

* Caso haja algum **pod, svc ou deployment** etc listado no passo anterior, limpar o cluster através do comando `kubectl delete all --all` e `kubectl delete pvc --all`
* Baixe o projeto QuickOrder-Infra-Kubernetes do repositório https://github.com/TechChallenge-4SOAT-G74/QuickOrder-Infra-Kubernetes.git
* Verifique os sprits do repositório digitando `ls` 

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/616de0f5-6919-4cd5-b24c-02221f520511)



<br />

* Aplicar os **scripts yml** dos **PersistentVolumeClaim** através do comando `kubectl apply -f .\01-pvc\`:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/22c32deb-51ca-4dc6-85c3-6a47ebfd2fbf)



<br />

* Aplicar os **scripts yml** dos **Deployments** através do comando `kubectl apply -f .\02-deployments\`:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/3226bd83-292f-44cb-a76f-23055fe51380)


<br />

* Aplicar os **scripts yml** dos **Services** através do comando `kubectl apply -f .\03-services\`:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/cbdf8d14-72e7-4869-a591-7f68edda991e)


<br />

* Executar comando `kubectl get all` para verificar a criação dos itens dos passos anteriores. O resultado deverá ser similar ao listado abaixo:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/eae9f6e1-5d0d-4104-bc7e-c712ed09835d)


<br />

* Abrir o browser e digitar o seguinte endereço **http://localhost:30000/swagger/index.html**. O swagger da Api deverá ser exibido, indicando que a subida da aplicação ocorreu com sucesso:

<br />

![image](https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/f8116e81-39f2-4659-9fe4-b814b552ab51)


<br />

**Passo a passo em vídeo Kubernetes**

<br />

<div align="center">
      <a href="https://www.youtube.com/watch?v=GJAberOaVkc">
     <img src="https://github.com/TechChallenge-4SOAT-G74/QuickOrder-backend/assets/44347862/163fddfb-86f0-4f2b-9591-81d0e6f3715d"
      alt="Kubernetes" 
      style="width:560px;height:315px;">
      </a>
</div>

<br />


