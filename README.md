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

---

# 🔬 Realizando o LAB - AI - Azure - SEARCH EXPLORER: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Após Preparação do Ambiente ter sido Finalizado com Sucesso. Vamos iniciar o LAB)

<br>

## 1 - Acesse o `Portal Azure`: <a href="https://portal.azure.com"> <img width="99" alt="https://portal.azure.com" src="https://github.com/mstrulenque/dio-lab-azure-ML/assets/63933792/4665d721-98e7-4c24-bc97-f7540d64a917"></a> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; https://portal.azure.com

## 2 - Faça o Login com a sua Conta 🔐


## 3 - Acesse o `Search Explorer`

3.1 - Selecione o Resource `AI Search` que criamos para o LAB: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.1.1 - Na página `Home` - `Resources - Recent`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Clique na Nome da Instancia do Recurso `AI Search` que criamos para o LAB ; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="620" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/2daa7b8b-f2f5-416a-9f1c-4cb1e1a35582">


3.2 - Selecione o `Search Explorer`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.1 - Na página `Instancia - AI Search` criada para o LAB: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Clique em `Search Explorer`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="620" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/8009e35d-b5a5-4e0a-a697-db24cd904b20">


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.2.2 - Na página `Search Explorer` - Altere a View: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Clique em `View` e escolha `JSON view`; <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="610" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/378a1b72-5856-4373-9435-5ba489a577ac">


---
3.3 - Execute LAB: <br>

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1 - `Search 01: Contar Todas as Reviews importadas`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1.1 - `Index` - escolher o Index que criamos para o LAB <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1.2 - `JSON query editor` - Consulta que queremos executar no formato JSON <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Copie o JSON abaixo e cole no campo `JSON query editor`<br>

```
{
    "search": "*",
    "count": true
}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1.3 - Clique no botão `Search` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1.4 - O Resultado da Pesquisa será apresentada no campo `Results` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.1.5 - Verifique os resultados apresentados <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="586" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/88c589bd-4c7d-4d6f-8010-8c989b5da808">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  OBS: o arquivo JSON completo gerado no resultado desta pesquisa está neste repositorio: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    >> [output/Teste-01_count_todos.json](https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/blob/main/output/Teste-01_count_todos.json)

<br>

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2 - `Search 02: Contar os Reviews de Chicago`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2.1 - `Index` - escolher o Index que criamos para o LAB <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2.2 - `JSON query editor` - Consulta que queremos executar no formato JSON <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Copie o JSON abaixo e cole no campo `JSON query editor`<br>

```
{
 "search": "locations:'Chicago'",
 "count": true
}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2.3 - Clique no botão `Search` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2.4 - O Resultado da Pesquisa será apresentada no campo `Results` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.2.5 - Verifique os resultados apresentados <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="586" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/426daf89-a9b2-4408-8f07-22b9fa345ebe">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  OBS: o arquivo JSON completo gerado no resultado desta pesquisa está neste repositorio: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    >> [output/Teste-02_count_location-chicago.json](https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/blob/main/output/Teste-02_count_location-chicago.json)

<br>

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3 - `Search 03: Contar os Reviews Com Sentimento Negativo`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3.1 - `Index` - escolher o Index que criamos para o LAB <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3.2 - `JSON query editor` - Consulta que queremos executar no formato JSON <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Copie o JSON abaixo e cole no campo `JSON query editor`<br>

```
{
 "search": "sentiment:'negative'",
 "count": true
}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3.3 - Clique no botão `Search` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3.4 - O Resultado da Pesquisa será apresentada no campo `Results` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.3.5 - Verifique os resultados apresentados <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="586" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/2475ce75-2c34-4eb5-b50b-3f416e44f8e7">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  OBS: o arquivo JSON completo gerado no resultado desta pesquisa está neste repositorio: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    >> [output/Teste-03_count_ssentiment-negative.json](https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/blob/main/output/Teste-03_count_sentiment-negative.json)


<br>

---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4 - `Search 04: Contar os Reviews Com Sentimento Positivo`: <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4.1 - `Index` - escolher o Index que criamos para o LAB <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4.2 - `JSON query editor` - Consulta que queremos executar no formato JSON <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  Copie o JSON abaixo e cole no campo `JSON query editor`<br>

```
{
 "search": "sentiment:'positive'",
 "count": true
}
```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4.3 - Clique no botão `Search` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4.4 - O Resultado da Pesquisa será apresentada no campo `Results` <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
3.3.4.5 - Verifique os resultados apresentados <br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img width="586" alt="image" src="https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/assets/63933792/b23aeac0-5453-4d4b-8ef8-fa4c44ca661a">

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
     ▶️  OBS: o arquivo JSON completo gerado no resultado desta pesquisa está neste repositorio: <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    >> [output/Teste-04_count_ssentiment-positive.json](https://github.com/mstrulenque/AI-Azure-Search-Explorer_LAB/blob/main/output/Teste-04_count_sentiment-positive.json)

---

<br>
<br>

