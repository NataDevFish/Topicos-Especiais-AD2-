# 🐢 Topicos especiais: projeção registro de Fauna Marinha

Este repositório contém os arquivos e os dados gerados em um projeto de **Processamento de Linguagem Natural (NLP)** e vetorização de textos. O projeto explora a geração e a projeção espacial de *embeddings* (representações vetoriais de palavras e documentos) a partir de um conjunto de dados reais de monitoramento de praias e ocorrências de fauna litorânea no estado de Santa Catarina.

## 🎯 Objetivo do Projeto
O objetivo principal desta atividade foi processar relatórios técnicos estruturados e transformar a linguagem humana em matrizes matemáticas utilizando modelos avançados de IA (como a arquitetura **BERT**). 

Com os tensores gerados, os dados foram projetados em um espaço tridimensional utilizando o **TensorFlow Embedding Projector**. Isso permitiu a análise visual do agrupamento (*clustering*) semântico de características biológicas (como espécies, estágio de vida e condição de carcaça) e ambientais (como tipo de ambiente, maré e direção do vento).

## 🗂️ Estrutura do Repositório

O repositório está organizado da seguinte forma para facilitar a reprodução do experimento:

* **`/` (Raiz):** Contém os *arquivos* (`.tsv`) os quais foram gerados pelos notebooks no Google Colab. Os notebooks são responsáveis pelo pipeline completo: segmentação, extração de metadados e geração dos tensores de projeção (vetores de 768 dimensões).
    * `3_2_1_GerarArquivosProjecaoEmbeddingsDocumento_v1.ipynb`
    * `3_2_2_GerarArquivosProjecaoEmbeddingsToken_v1.ipynb`
    * `3_2_3_GerarArquivosProjecaoEmbeddingsToken_Documento_v1.ipynb`
    * `3_2_4_GerarArquivosProjecaoEmbeddingsSentenca_Documento_v1.ipynb`
* **`/projecao`:** Pasta contendo os artefatos finais gerados pelos notebooks no formato `.tsv`. Para cada etapa, há um arquivo `records_*.tsv` (vetores numéricos) e um arquivo `meta_*.tsv` (os metadados em texto para rotulação no gráfico).

## 🛠️ Tecnologias Utilizadas
* **Linguagem:** Python
* **Bibliotecas Principais:** `pandas`, `transformers` (Hugging Face / BERT), `PyTorch`
* **Visualização de Dados:** [TensorFlow Embedding Projector](https://projector.tensorflow.org/)

## 🔬 Principais Conclusões da Análise
As projeções geométricas provaram que o modelo de Inteligência Artificial foi capaz de capturar e estruturar o contexto biológico dos relatórios. 

1. **Agrupamento de Documentos:** O modelo criou sub-regiões no espaço vetorial para diferenciar desfechos biológicos, agrupando espacialmente ocorrências com as mesmas características de encalhe.
2. **Proximidade Semântica (Tokens):** Tokens referentes a municípios geograficamente próximos (ex: Bombinhas, Porto Belo, Itapema) foram projetados na mesma vizinhança geométrica.
3. **Mapeamento Morfossintático:** No espaço compartilhado, identificou-se que tokens de classes gramaticais estruturais (como substantivos e nomes próprios) funcionam como eixos de atração, agrupando ao seu redor os documentos completos que os utilizam como base descritiva.

---
*Projeto desenvolvido como requisito para a disciplina de Tópicos Especiais / Sistemas de Recuperação da Informação (Avaliação a Distância - AD2).*
