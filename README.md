# Desafios de Projetos
Este repositório contém anotações relacionadas aos desafios de projetos elaborados para os cursos realizados na DIO.

## Desafio de Projeto: Criando um Assistente de Delivery com AWS Step Functions e Bedrock

- Acessar AWS Step Functions;
- Clicar em `Criar Máquina de Estado`;
- Selecionar modelo e clicar em implatar e executar, pois o modelo estará em "Somente leitura";
- Clicar em `Editar` modelo;
- Permissão Nível 1:
  * Acessar `Configuração` → `Perfil de execução` → `Visualizar no IAM`
  * Clicar em `Adicionar permissões` → `Anexar políticas`
  * Selecionar as políticas necessárias e clicar em `Adicionar`
- Ao clicar em cada uma das aplicações (blocos do workflow), selecionar o modelo LLM que será utilizado (Ex.: Haiku, Sonnet, Opus) e salvar;
- Em `Configuração` do bloco da aplicação:
  * Alterar o máximo de tokens;
  * Dentro de content → text: adicionar o prompt;
- Na aba `Saída` do bloco, adicionar o resultado em uma variável. Ex.:
```
{
  "result_one.$": "$.Body.content[0].text"
}
```
- O bloco "Pass state", recebe "result_one", combina com "prompt_one" e guarda na variável "convo_one";
- Nos outros blocos, é possível realizar as mesmas configurações realizadas no primeiro bloco (quantidade de tokens, definição de prompt, armazenamento em variável);
- `Salvar` e `Executar` o modelo;
- Na aba de Iniciar execução, é possível adicionar entradas adicionais (opcional).
- Clicar em `Iniciar execução`;
- Após iniciada a execução, é possível consultar o `Event view` e `State view`.

## Desafio de Projeto: Trabalhando com Machine Learning na Prática no Azure ML 

Tudo que é possível ter em um ambiente on premise, é possível ter em um ambiente em nuvem.

### Serviços de IA no Microsoft Azure
- Aprendizado de Máquina Azure: uma plataforma para treinar, implantar e gerenciar modelos de aprendizado de máquina
- Serviços de IA do Azure: um conjunto de serviços que abrange visão, fala, linguagem, decisão e IA generativa
- Pesquisa Cognitiva do Azure: Extração, enriquecimento e indexação de dados para pesquisa inteligente e mineração de conhecimento.

### Criando maáquinas virtuais no Azure

- Acessar o dashboard do Microsoft Azure;
- Clicar em `Criar um recurso` e pesquisar por Machine Learning;
- Clicar em `Create` e preencher as informações necessárias (subscription, resource group, name – que deve ser único –, region, stoarage account, key vault, application insights, container registry);
- Clique em `Review + Create`;
- Ao abrir o recurso, clique em `Launch Studio` que irá redirecionar para a página ml.azure.com;
- Na barra lateral, ir na opção `ML automatizado` e clicar em `Novo trabalho de ML automatizado`;
- Preencher as informaçãoes para criar ativo de dados;

### Pontos de Extremidade do Azure
O Azure oferece dois tipos de pontos de extremidade para acessar compartilhamentos de arquivos do Azure:
- Pontos de extremindade públicos: têm endereço IP público e podem ser acessados de qualquer lugador do mundo;
- Pontos de extremidade privados: existem em uma rede virtual e têm um endereço de IP privado dentro do espaço de endereço dessa rede virtual.

Pontos de extremidade públicos e privados existem na conta de armazenamento do Azure. 

#### Links úteis:

- [Configurar pontos de extremidade de rede para acessar compartilhamentos de arquivos do Azure](https://learn.microsoft.com/pt-br/azure/storage/files/storage-files-networking-endpoints?tabs=azure-portal)
- [Explore Azure AI Services](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html)
- [Explore Automated Machine Learning in Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

## Desafio de Projeto: Reconhecimento Facial e transformação de imagens em Dados no Azure ML 

O serviço Azure AI Vision dá acesso à algoritmos avançados que processam imagens e retornam informações com base nos recursos visuais. 

| Serviço | Descrição |
|---------|-----------|
| Reconhecimento Óptico de Caracteres (OCR) | O serviço de Reconhecimento Óptico de Caracteres (OCR) extrai texto de imagens. |
| Análise de Imagem | O serviço Image Analysis extrai muitos recursos visuais de imagens, como objetos, rostos, conteúdo adulto e descrições de texto geradas automaticamente. |
| Face | O serviço Face fornece algoritmos de IA que detectam, reconhecem e analisam rostos humanos em imagens. |
| Análise de Vídeo | A Análise de Vídeo inclui recursos relacionados a vídeo, como Análise Espacial e Recuperação de Vídeo. A Análise Espacial analisa a presença e o movimento de pessoas em um feed de vídeo e produz eventos aos quais outros sistemas podem responder. |
*Fonte: Microsoft*


#### Links úteis:
- [What is Azure AI Vision?](https://learn.microsoft.com/en-us/azure/ai-services/computer-vision/overview)

### Passo a passo
- Acessar o dashboard do Microsoft Azure;
- Clicar em `Criar um recurso` e pesquisar por Azure AI Services;
- Clicar em `Create` e preencher as informações necessárias (subscription, resource group, region, name, pricing tier);
- Clicar em `Review + Create`;
- Acessar o portal do [Vision Studio](http://portal.vision.cognitive.azure.com);
- Acessar `My resources`;
- Selecionar o recurso que foi criado e clicar em `Select as default resource`.

## Desafio de Projeto: Análise de Sentimentos com Language Studio no Azure AI

O Language Studio é um conjunto de ferramentas baseadas em interface de usuário que permite explorar, criar e integrar recursos de Linaguem da IA do Azure aos aplicativos. 

### Serviço de bot do Azure
- Plataforma baseada em nuvem para desenvolvimento e gerenciamento de bots;
- Integração com AI Language e outros serviços;
- Conectividade atráves de vários canais.

### Reconhecimento e síntese de fala
- Use recursos de fala para texto do serviço **Fala** para transcrever fala audível em texto;
- Use os recursos de conversão de texto em fala do **Serviço de Fala** para gerar fala audível a partir de texto.

### Passo a Passo 1
- Acesso o portal speech.microsoft.com;
- Crie um novo recurso;
- Acesse `Conversão de Fala em Texto em Tempo Real`;
- Importe o áudio;
- Configure as próximas etapas

### Passo a Passo Language Studio
- Acesse o dashboard do Azure;
- Clique em `Create a resource` e em `Language Service`;
- Clique em criar `Create` e preencha as informações (subscription, resource group, region, name, pricing tier);
- Clique em `Review + Create`;
- Acesse o portal [Language Studio](http://language.cognitive.azure.com)
- Filtre pela aba `Classify text` e selecione `Analyze sentiment and mine opinions`;
- Comece a realizar os testes com texto. 

## Desafio de Código: Azure Cognitive Search: Utilizando AI Search para indexação e consulta de dados 
Mineração de conhecimento: encontra insights em escala, como palavras-chave, frases-chave etc.;
O Azure Cognitive Search é a plataforma de mineração de conhecimento alimentada por IA do Azure;

### Soluções de pesquisa cognitiva do Azure
Ingestão de dados
- Azure Blob Storage containers;
- Azure Data Lake Storage Gen2;
- Azure Table Storage.

Enriquecimento e índice de IA
- Permite uma compreensão mais profunda;
- Visão, Processamento de Linguagem Natural etc;
- A indexação torna o conteúdo pesquisável.

Explorar
- Pesquisa realizada em índices;
- Dentro dos aplicativos;
- Crie visualizações de dados.

### Passo a passo no portal
- Acesse o dashboard do Azure;
- Clique em `AI Search`;
- Clique em `Create` e preencher as informações necessárias (subscription, resource group, region, name, pricing tier: nível Basic);
- Clique em `Review + Create`;
- Clique em `Create a resource` e em `Azure AI Services`
- Clique em criar `Create` e preencha as informações (subscription, resource group, region, name, pricing tier: Standard S0);
- Clicar em `Review + Create`;
- Clique em `Store accounts`;
- Clique em `Create` e preencha as informações (subscription, resource group, storage account name, region, perfomance e redundancy: locally-redundant storage (LRS));
- Clique em `Review` e `Create`;

Dentro do Storage account:
- Acesse configuração;
- Habilite o acesso por anônimos;
- Clique em `salvar`.
- Vá em `Data Storage` e Clique em `Containers` e em `+ Container`;
- Adicione o nome do container;
- Acesse o container criado e clique em `upload` e selecione os arquivos

AI Search: 
- Acesse o AI Search;
- Clique em `Import data`;
- Selecione onde estão os dados e o que gostaria de fazer com os dados;
  
