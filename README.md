# Consulta de CNPJ na Receita Federal

Automação de consulta em lote de CNPJs, criada para apoiar a cobrança da dívida ativa
na Prefeitura de Ilhabela.

> **Este repositório não contém código.** Ele existe para registrar o problema e a
> solução. O código fica em repositório privado, porque a lista de contribuintes que
> ele processa é dado fiscal do município.

## O problema

A cobrança de dívida ativa depende de saber a situação cadastral de cada devedor
pessoa jurídica: se a empresa ainda está ativa, qual é o endereço vigente, quem
responde por ela. Essa conferência era feita uma empresa por vez, no site da Receita,
copiando o resultado à mão para uma planilha. Com centenas de inscrições na fila, a
conferência consumia o tempo que deveria ir para a cobrança em si.

## A solução

Uma ferramenta em Python que recebe a lista de CNPJs e devolve uma planilha pronta
para o departamento trabalhar:

- consulta em lote nas APIs **ReceitaWS** e **CNPJ.ws**, uma complementando a outra;
- trata o limite de requisições das duas APIs, com espera e retomada, para a lista
  inteira ser processada sem intervenção;
- consolida o retorno em **Excel**, no formato que a Dívida Ativa e Cadastro já usa.

## Situação

Construída como proposta para o departamento de Dívida Ativa e Cadastro. Fora do
expediente, por iniciativa própria, a partir de um gargalo que eu via no dia a dia
do Controle Interno.

## Por que o código é fechado

A entrada da ferramenta é a relação de CNPJs em cobrança do município. Mesmo sem os
dados no repositório, publicar o código exporia o formato dos arquivos internos e a
forma como a Prefeitura organiza essa base. Preferi manter fechado.

Se você quiser ver o mesmo tipo de trabalho com o código aberto, estes dois
repositórios usam dados fictícios e podem ser executados:

- [checklist-documental-ia](https://github.com/danilabm/checklist-documental-ia) —
  agente que confere os documentos de um processo contra a lista de exigências
- [triagem-inclusiva-ia](https://github.com/danilabm/triagem-inclusiva-ia) —
  anonimização de currículos e roteiro de entrevista estruturada

## Stack

Python · APIs REST · ReceitaWS · CNPJ.ws · Excel

---

Danila Almanadily — [portfólio](https://danilabm.github.io/Portfolio/) ·
[LinkedIn](https://www.linkedin.com/in/danilabm/)
