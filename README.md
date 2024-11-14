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
