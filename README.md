# Reconhecimento de Entidades Nomeadas com Arquitetura LSTM

Este projeto apresenta a implementação de um método para a identificação automática de entidades nomeadas em textos, utilizando técnicas consolidadas de Processamento de Linguagem Natural (PLN) e Aprendizado de Máquina. O núcleo da aplicação baseia-se em uma arquitetura de rede neural recorrente com unidades LSTM (Long Short-Term Memory), configurada para interpretar, segmentar e classificar tokens segundo o paradigma NER (Named Entity Recognition).

O objetivo central consiste em aplicar uma abordagem algorítmica capaz de reconhecer entidades previamente definidas, como nomes próprios, localizações geográficas e instituições, utilizando para tal um corpus anotado em formato padronizado.

## Objetivos da Aplicação

- Implementar um modelo baseado em rede neural com estrutura LSTM para execução da tarefa de NER.
- Realizar o pré-processamento das sequências textuais com tokenização e anotação segundo a convenção BIO (Begin, Inside, Outside).
- Avaliar o desempenho do modelo por meio de métricas específicas para tarefas sequenciais, como F1-score.
- Aplicar técnicas de embeddings e alinhamento vetorial com `pad_sequences` para uniformização das entradas.
- Validar a robustez do modelo em textos não previamente vistos.

## Base de Dados

- **Fonte:** Kaggle – Entity Annotated Corpus  
- **Nome:** Groningen Meaning Bank (GMB)  
- **Formato:** Arquivo CSV (`ner_dataset.csv`) com as seguintes colunas:
  - `Sentence #`: identificação única da sentença
  - `Word`: token individual
  - `POS`: classe gramatical associada
  - `Tag`: anotação BIO da entidade

- **Tipo de tarefa:** Reconhecimento de Entidades Nomeadas com codificação BIO.

## Etapas Metodológicas

1. Leitura estruturada e sanitização do arquivo `ner.csv`.
2. Agrupamento de tokens por sentença e extração das sequências anotadas.
3. Mapeamento de tokens e labels para índices inteiros.
4. Aplicação das funções `pad_sequences` e `to_categorical` para adequação ao formato da rede.
5. Treinamento do modelo utilizando LSTM bidirecional com configuração adequada ao problema de sequência.
6. Avaliação do desempenho por meio de métricas de sequência (como `precision`, `recall` e `F1-score`).
7. Visualização das predições em exemplos reais, a fim de verificar a acurácia qualitativa do modelo.

## Bibliotecas Utilizadas

- `python 3.x` - linguagem base;
- `pandas`, `numpy` – manipulação e tratamento de dados;
- `matplotlib` – geração de gráficos e visualizações (opcional);  
- `scikit-learn`, `tensorflow.keras`– construção e avaliação dos modelos.

## Organização do Repositório

```bash
├── data/
│   └── ner_dataset.csv            # Base de dados anotada (GMB)
├── lstm_ner.ipynb                 # Implementação do modelo com arquitetura LSTM
├── README.md                      # Documento de descrição do projeto e instruções
