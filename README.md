# AI-Azure-Search-Explorer_LAB


---

`LAB Utilizando` : Microsoft **Azure AI | Search Explorer**

`Descrição do LAB` : 

LAB - com o passo-a-passo em texto e print screen, configurando os recursos: AI Search, AI Services e um Storage onde será criado um container que iremos fazer o upload de 9 arquivos word (com imagens e textos de review sobre uma franquia ficticia de Café) e indexar estes arquivos, para conseguirmos através do Search Explorer realizar pesquisas de quantidades de review positivos, negativos, realizados em determinada cidade, etc).
     
`Ações que serão realizadas` :

- PREPARAÇÃO:

   - `Azure`:
     - Criar um Resource Group
     - Provisionar os Resources:
       -  `AI Search`
       -  `Azure AI Services`
       -  `Storage Account`
         - Criar Container
         - Realizar Upload de 9 arquivos word
         - Criar um Data Source
         - Configurar Skillsets
           - habilitação do OCR
           - Texto: extração de informações de sentimentos, key phrases e localizacao
           - Imagens: gerar descrição do conteúdo das imagens e tag's  

- LAB:
     
     - Search Explorer:
       -  Pesquisar:
         - quantidade de reviews sobre café realizados no total
         - quantidade de reviews sobre café da franquia de Chicago
         - quantidade de reviews sobre café com sentimento - negativo
         - quantidade de reviews sobre café com sentimento - positivo
     
  
`Arquivos deste Repositório GitHub` : <br>

&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `README.MD` - Passo-a-Passo com Print Screen's; <br>

&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `input/*`   - arquivos WORD com imagens e textos dos reviews sobre café; <br>

&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `output/*`  - arquivos JSON com os resultados das pesquisas realizadas no LAB<br>

---

# 👷 - Preparando Ambiente para realizar o LAB: 


## 1 - Acesse o `Portal Azure`: <a href="https://portal.azure.com"> <img width="99" alt="https://portal.azure.com" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/4665d721-98e7-4c24-bc97-f7540d64a917"></a> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://portal.azure.com

## 2 - Faça o Login com a sua Conta 🔐
  
## 3 - Provisionamento do Resource `AI Search`

3.1 - Encontre o Resource `AI Search`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Home` - Clique no Item de Menu `All services`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `All Services` - Clique no Item de Menu `AI + machine learning`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `All Services` - Procure o Item `AI Search` e Clique no `+` (Create); <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="404" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/06033244-c09e-451d-a0b7-b3e5a4f45b15">


3.2 - Criando o Recurso `Search Service`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1 - Preencher informações - `Project Details` e `Instance Details`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.1 - `Subscription` - Selecione a sua Subscription; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.2 - `Resource Group` - Clique no link `Create New` abaixo do campo; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.3 - `Resource Group` - Digite um nome para seu Resource Group; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.4 - `Resource Group` - Clique no botão `OK`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.5 - `Resource Group` - o nome que você criou aparecerá selecionado no campo de escolha "Resource Group", <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
caso contrário escolha na lista; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="413" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/f2c5e895-6f81-470b-aaac-f394513d6dc8">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.6 - `Service Name` (instance) - preencher o nome da Instancia do Recurso "AI Search" que está sendo criado <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1.7 - `Location` - selecionar a Location que deseja que o Resource seja provisionado<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="317" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/50bc87a6-a7fc-427e-b2f3-5fb010293429">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2 - Preencher informações - `Instance Details - Pricing tier`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2.1 - Clicar no Link: `Change Pricing tier`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2.2 - Escolher na Lista `Select Pricing tier` a opção: `Basic`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="397" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/c15b5de0-1681-45bf-9508-cbabea977dea">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.3 - Na página `Create a Search service` - Clicar no Botão - `Review + Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="317" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/6f9487e5-57fa-470e-963e-da399d6cf023">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.4 - Revise os Dados e estando tudo correto, Clique no botão `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="361" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/f00296a5-b5b0-4dd5-bb4e-662978d84b3b">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.5 - Após a confirmação o Deploy iniciará, e ao final será apresentada uma pagina similar a pagina abaixo: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="521" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/2d75d171-7e95-4044-a135-cb59ed2e247b">


## 4 - Provisionamento do Resource `AI Services`

4.1 - Encontre o Resource `AI Services`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Home` - Clique em `+ Create a Resource`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Create a Resource` - Clique no Item de Menu `AI + machine learning`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Create a Resource` - Procure o Item `Azure AI Services` e Clique no link: `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="327" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/981eb303-70f2-4910-ba99-6135ef0eaa22">

4.2 - Criando o Recurso `Azure AI Services`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1 - Preencher informações - `Project Details` e `Instance Details`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.1 - `Subscription` - Selecione a sua Subscription; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.2 - `Resource Group` - Selecione na lista de opções o "Resource Group" criado previamente (Resource "Search Service"; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.3 - `Region` - selecionar a Region que deseja que o Resource seja provisionado<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.4 - `Name` (instance) - preencher o nome da Instancia do Recurso "Azure AI Services" que está sendo criado <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.5 - `Pricing Tier` - Selecione no campo de escolha a opção: `Standard S0` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.1.6 - Clique no Botão - `Review + Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="357" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/5f17c9cc-c3cd-4e1c-b807-495c8185d83b">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.2 - Revise os Dados e estando tudo correto, Clique no botão `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="357" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/04b2e90d-703d-4067-b4db-71bd4b61df4d">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
4.2.3 - Após a confirmação o Deploy iniciará, e ao final será apresentada uma pagina similar a pagina abaixo: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="419" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/384a9042-c954-453a-abee-b70a3d0b841c">


## 5 - Provisionamento do Resource `Storage Account`

5.1 - Encontre o Resource `Storage Account`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Home` - Clique em `+ Create a Resource`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Create a Resource` - Clique no Item de Menu `Storage`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Create a Resource` - Procure o Item `Storage Account` e Clique no link: `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="286" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/590f7e1a-6ce1-44ac-8a9f-789ca5e4384d">

5.2 - Criando o Recurso `Storage Account`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1 - Preencher informações - `Project Details` e `Instance Details`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.1 - `Subscription` - Selecione a sua Subscription; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.2 - `Resource Group` - Selecione na lista de opções o "Resource Group" criado previamente (Resource "Search Service"; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.3 - `Storage Account Name` (instance) - preencher o nome da Instancia do Recurso "Storage Account" que está sendo criado <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.4 - `Region` - selecionar a Region que deseja que o Resource seja provisionado<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.5 - `Performance` - Selecione a opção: `Standard` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.6 - `Redundancy` - Selecione a opção: `Locally-Redundant Storage (LRS) ` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.1.7 - Clique no Botão - `Review + Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="410" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/579f3bf8-9b7e-48e0-83ef-bc9abfcd46b4">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.2 - Revise os Dados e estando tudo correto, Clique no botão `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="410" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/18f9eebc-3bec-4c39-b49d-764b1416bdbc">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.2.3 - Após a confirmação o Deploy iniciará, e ao final será apresentada uma pagina similar a pagina abaixo: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="477" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/95320c49-5fe8-455a-8220-4a6fa50064c8">


## 6 - Configurando o `Storage Account`

6.1 - `Acessando o Storage Account` provisionado para o LAB: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Home` - Clique no item de Menu `Storage Accounts`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Storage Accounts` - Clique no Link do nome da instancia "Storage Account" criado para o LAB; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="395" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/f71bf3dc-7873-43f5-a949-2920b688983e">

6.2 - Configurando `Anonymous Access`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.2.1 - na página `Storage Accounts` da Instancia  - Clicar no Menu `Configuration`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.2.2 - na página `Storage Accounts` da Instancia  - No item `Allow Blob anonymous access`, escolher a opção: `Enabled`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.2.3 - na página `Storage Accounts` da Instancia  - Clicar em: `Salve`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="447" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/2e34b637-1ea2-45fd-98e5-247604daaac9">

6.3 - `Container - Criando`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.1 - na página `Storage Accounts` da Instancia  - Clicar no Menu `Data Storage > Containers`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.2 - na página `Storage Accounts` da Instancia  - Clicar em `+ Container`, para criar um Novo Container; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.2.1 - no box `New Container` - Campo `Name`, preencher um nome para o Novo Container; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.2.2 - no box `New Container` - Campo `Anonymous access Level`, escolher opção: `Container (anonymous read access for container e blobs)`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.2.2 - no box `New Container` - Clicar no botão `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="633" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/d101972b-bb55-4c99-b1ab-27cfa9b6e82d">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.3.2.3 - Container Criado; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="644" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/7f21c2c8-2bcc-4cf9-8edb-537b8ca22f80">

6.4 - `Container - Upload Arquivos`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.1 - Baixando `da Microsoft` os arquivos: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.1.1 - Acessar `https://aka.ms/mslearn-coffee-reviews` - Com isto um arquivo zip será baixado na sua maquina; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.2 - `Descompactar arquivo zip`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="390" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/751566c0-950e-46e7-b71b-67f820643b20">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
**OBS: estes arquivos encontram-se também neste repositório do GitHub** ▶️ [pasta input](https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/tree/main/input)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3 - `Upload dos Arquivos`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.1 - Acessar o Container Criado - Clicando no Link do Nome do Container; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="644" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explore_LAB/assets/63933792/7f21c2c8-2bcc-4cf9-8edb-537b8ca22f80">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.2 - Na página do `Container` - Clicar em `Upload` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.3 - No Box `Upload Blob` - Acessar os arquivos word descompactados e `Drag and Drop` ou fazer `Browser` dos arquivos; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.4 - No Box `Upload Blob` - Selecionar a caixa de seleção `Overrite if files already exists`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.5 - No Box `Upload Blob` - Clicar no botão `Upload`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="561" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/f4687aac-cebd-4a0a-b64d-4b8466c87a40">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
6.4.3.6 - `Arquivos Importados para o Container`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="561" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/40742ed9-ee79-4448-822a-74ddaefea024">


## 7 - Configurando o `AI Search`

7.1 - `Acessando o AI Search Service` provisionado para o LAB: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página `Home` - "Resources - Recent" - Clique no link do nome dado a instancia do `AI Search`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Na página da Instancia do `Recurso - AI Search` - Clique em `Import Data`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="367" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/4c688737-266f-4e58-940a-e8e12ca81efd">

7.2 - Configurando `DATA SOURCE`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1 - na página `Import Data`, preencher os campos `Data Source`: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.1 - `Data Source` (tipo) - escolha: `Azure Blob Storage`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.2 - `Data Source name` - digite um nome para o Data Source; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.3 - `Data to extract` - escolha: `Content and Metadata`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.4 - `Parsing Mode` - escolha: `Default`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.5 - `Connection String` - clique no link: `Choose an existing connection`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.6 - `Connection String` - página `Storage Accounts` - clique no link com o nome da Storage que criamos p/ este LAB; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.7 - `Connection String` - página `Containers` - Escolha o Container que criamos p/ este LAB; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.8 - `Connection String` - página `Containers` - Clique no botão `Select`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="367" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/21eae5ad-9ad3-4ab8-8b15-7f2f48f66877">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="285" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/d49506a9-8419-45e9-bafc-f609a49b0766">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.9 - na página `Import Data`, campo: `Managed Identity authentication` - escolher opção: `None`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.2.1.10 - na página `Import Data`, clicar no botão: `Next: Add cognitive skills (optional)`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="285" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/3a5fdd59-b627-424b-914a-c02d6eb1799d">

7.3 - Configurando `SKILLSET`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1 - ainda na página `Import Data`, preencher os campos `Skillset`: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.1 - `AI Services Resource Name` - escolha o Resource `AI Services` que provisionamos para o LAB; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="285" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/2844d0ea-1455-414f-b01e-5eca13737d17">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.2 - `Skillset Name` - digite um nome para o Skillset que iremos configurar; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.3 - Selecione a opção `Enable OCR and merge all text into merged_content field`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.4 - `Source Data field` - escolha: `merged_content`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.5 - Selecione os Itens `Text and Image Skills` abaixo: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Extract location names`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Extract key phrases`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Detect sentiment`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Image Cognitive Skills`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Generate tags from Images`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Generate captions from Images`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="320" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/748405ab-2c50-4962-ab4c-cd4e802bb148">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.3.1.6 - Selecione os Itens `Azure file projections` abaixo: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Image Projections`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Pages - Key phrases`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Pages - Entities`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Image Details - Image References`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Azure blob projections - Document`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  `Container Name`: Selecione o Container que criamos para o LAB;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
▶️  Clique em `Next: Customize target index`;

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="300" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/477bac06-c8fd-49aa-a88b-6284f00b9248">


7.4 - Configurando `INDEX`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.4.1 - ainda na página `Import Data`, preencher os campos `Index`: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.4.1.1 - `Index Name` - digite um nome para o Index; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.4.1.2 - `Key` = `metadata_storage_path`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.4.1.3 - Selecionar a coluna `Filtrable` para todos os campos que vieram marcados quando entramos na pagina; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.4.1.4 - Clicar no botão `Next: Create a Indexer`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="334" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/c6700760-78ec-4166-bb90-7f5564a27b95">


7.5 - Criando um `INDEXER` (Job que irá executar a indexação): <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.5.1 - ainda na página `Import Data`, preencher os campos `Indexer`: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.5.1.1 - `Indexer  Name` - digite um nome para o Indexer; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.5.1.2 - `Schedule` - escolher `Once` (assim que criado ele executa o Job uma vez); <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.5.1.3 - `Advanced options - Base-64 Encode Keys` -> `Selecionar`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
7.5.1.4 - Clicar no Botão `Submit`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="334" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/c23ef05c-1ba3-4ca6-8dfe-8ceca23fe7cd">


7.6 - `Visão das Configurações realizadas no Resource - AI - SEARCH` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="520" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/9931807d-14d0-4a43-87b8-87cf47ca843c">







****
EM ANDAMENTO ......
*****
*****











&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.3 - `Region` - escolha uma Region da Cloud para criação do workspace; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.4 - `Name` Instance = `instanceLanguageLab` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.5 - `Pricing tier` = `Free F0 (5K Transactions per 30 days)` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.6 - `Storage` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.6.1 - `New/Existing storage Account` - Clique em `New Storage Account`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.6.2 - `Storage Account Name` - digite um nome para a Storage Account; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.6.3 - `Storage Account Type` - escolha a Storage Account type; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.7 - Clique no botão `Review + Create`; <br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="436" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/3e27c53c-6978-4e2b-aa4e-22cadf4311da">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.8 - Revise os Dados e estando tudo correto, Clique no botão `Create`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="436" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/f2f0b96c-90a3-4fbe-beab-8d8edae0282f">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.4.9 - Após a confirmação o Deploy iniciará, e ao final será apresentada uma pagina similar a pagina abaixo: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="606" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/681248dd-bb7c-42f4-a5e1-e06405eb4a60">
<br>

## 4 - Acesse o `Language Studio`: <a href="https://language.cognitive.azure.com"> <img width="180" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/6fc4bdd0-80e6-4ab4-ae83-3c4e91bfc360">
</a> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://language.cognitive.azure.com
  
## 5 - Selecione o Resource, aprovisionado no passo acima, p/ utilização no Language Studio

5.1 - Assim que você logar, Na página `Home - Welcome to Language Studio`, Abrirá um popup - `Select an Azure resource`, preencha:
<br><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.1.1 - `Azure Subscription`: selecione a sua Subscription; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.1.2 - `Resource Type`: escolha `Language`; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.1.3 - `Resource Name`: escolha o Nome da Instancia que criou na Azure; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
5.1.4 - Clique no botão `Done`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="668" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/333407ca-fd4f-49fd-beed-f009cb0816be">

---

# 🔬 Realizando o LAB - AI - Azure - Language Studio (Sentiment Analysis): 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Após Preparação do Ambiente ter sido Finalizado com Sucesso. Vamos iniciar o LAB)

<br>

## 1 - Acesse o `Language Studio`: <a href="https://language.cognitive.azure.com"> <img width="180" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/6fc4bdd0-80e6-4ab4-ae83-3c4e91bfc360">
</a> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://language.cognitive.azure.com
  
## 2 - Escolher - `Language - Sentiment Analysis`

2.1 - Na página `Home - Welcome to Language Studio`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Clique na Guia `Classify Text` ; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Clique no box `Analyze sentiment and mine opinions` ; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="520" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/8c38b2e3-675f-46b5-98c1-7f149aefa68d">

## 3 - LAB - `Sentiment Analysis`

3.1 `TESTE - 01` - Texto 1 : `opiniao-celular-maria_p.txt` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.1 - `Select Text Language` (idioma) - Selecionar: `Portuguese (Brazil)` se for utilizar arquivo texto deste repositório GitHub: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.2 - `Azure Resource` - Selecionar o Resource que foi criado na Azure (Preparação do LAB) <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.3 - `Escolhendo o Texto 1`: `opiniao-celular-maria_p.txt` - pasta: `inputs` - deste repositório GitHub: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clicar no box `Browse a File` ; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Escolher o Arquivo `opiniao-celular-maria_p.txt` que fez download do repositorio GitHub p/ sua maquina; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Clique em `Abrir` ; <br>          

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="520" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/43913d1d-1646-4274-b225-aa8f16a75557">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="491" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/4dbe752a-1719-4a5e-8499-03d9b2783657">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.4 - `Executando o Teste - 01`
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clique no botão 'Run`;
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="475" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/0918be34-a9c0-4653-9ea4-864c06b614dc">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.5 - `Resultado do Processamento - Texto 1` pelo `Language Studio`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="577" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/3aa05320-5009-4149-a2b0-ee0f647ac387">


<br>
<br>

3.2 `TESTE - 02` - Texto 2 : `opiniao-celular-joao_n.txt` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1 - `Select Text Language` (idioma) - Selecionar: `Portuguese (Brazil)` se for utilizar arquivo texto deste repositório GitHub: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2 - `Azure Resource` - Selecionar o Resource que foi criado na Azure (Preparação do LAB) <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.3 - `Escolhendo o Texto 2`: `opiniao-celular-joao_n.txt` - pasta: `inputs` - deste repositório GitHub: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clicar no box `Browse a File` ; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Escolher o Arquivo `opiniao-celular-joao_n.txt` que fez download do repositorio GitHub p/ sua maquina; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Clique em `Abrir` ; <br>          

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="520" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/43913d1d-1646-4274-b225-aa8f16a75557">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="426" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/27771125-de79-4151-b2d7-218f34409d33">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.4 - `Executando o Teste - 02`
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clique no botão 'Run`;
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="475" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/0918be34-a9c0-4653-9ea4-864c06b614dc">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.5 - `Resultado do Processamento - Texto 2` pelo `Language Studio`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="644" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/a2ed7379-5f4d-422b-b59f-eeb20ace27b3">


<br>
<br>

3.3 `TESTE - 03` - Texto 3 : `opiniao-celular-jose_p_n.txt` <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1 - `Select Text Language` (idioma) - Selecionar: `Portuguese (Brazil)` se for utilizar arquivo texto deste repositório GitHub: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2 - `Azure Resource` - Selecionar o Resource que foi criado na Azure (Preparação do LAB) <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.3 - `Escolhendo o Texto 3`: `opiniao-celular-jose_p_n.txt` - pasta: `inputs` - deste repositório GitHub: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clicar no box `Browse a File` ; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Escolher o Arquivo `opiniao-celular-jose_p_n.txt` que fez download do repositorio GitHub p/ sua maquina; <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️ Clique em `Abrir` ; <br>          

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="520" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/43913d1d-1646-4274-b225-aa8f16a75557">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="394" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/277928ec-51d3-4747-8593-ed1fca715f4c">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.4 - `Executando o Teste - 03`
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          ▶️  Clique no botão 'Run`;
   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="351" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/588325ef-7ca4-4141-90f3-bcf84222c535">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.5 - `Resultado do Processamento - Texto 3` pelo `Language Studio`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="829" alt="image" src="https://github.com/mstrulenque/AI-Azure-Language-Studio_Analise-Sentimento_LAB/assets/63933792/2370283e-a34f-4953-b518-bc6a5bf89144">


<br>
<br>

