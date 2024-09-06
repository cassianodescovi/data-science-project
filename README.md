# Hybrid Recommendation System

Este projeto implementa um **Sistema de Recomendações Híbrido** que combina métodos de **Filtragem Colaborativa** e **Recomendações Baseadas em Conteúdo** para recomendar produtos a usuários com base em suas preferências e nas características dos itens.

## Funcionalidades

- **Recomendações Baseadas em Conteúdo**: Utiliza características dos produtos (tags, descrições, etc.) para recomendar itens semelhantes ao item fornecido.
- **Filtragem Colaborativa**: Utiliza similaridade entre usuários para recomendar itens que usuários semelhantes avaliaram.
- **Recomendações Híbridas**: Combina ambos os métodos (baseado em conteúdo e colaborativa) para fornecer uma lista consolidada de recomendações.

## Estrutura do Projeto

- `train_data`: DataFrame contendo os dados de treinamento, incluindo informações sobre produtos e avaliações.
- `content_based_recommendations()`: Função que gera recomendações baseadas em conteúdo, analisando as características dos itens.
- `collaborative_filtering_recommendations()`: Função que gera recomendações baseadas na similaridade de usuários.
- `hybrid_recommendations()`: Função que combina ambos os métodos de recomendação para fornecer uma lista híbrida.
  
## Tecnologias Utilizadas

- **Python**: Linguagem de programação principal.
- **Pandas**: Manipulação de dados.
- **scikit-learn**: Utilizada para cálculos de similaridade do cosseno e vetorização TF-IDF.
- **Cosine Similarity**: Medida de similaridade utilizada para encontrar produtos e usuários semelhantes.
- **TfidfVectorizer**: Utilizada para transformar texto (descrições de produtos) em vetores numéricos.

## Instalação

1. Clone este repositório:

   ```bash
   git clone https://github.com/seu-usuario/hybrid-recommendation-system.git
   ```
2. Instale as dependências:
  ```bash
  pip install -r requirements.txt
   ```
3. Certifique-se de que seu ambiente está configurado com as bibliotecas necessárias:
- `pandas`
- `scikit-learn`
- `numpy`

## Como Executar
Exemplo de Uso
1. Recomendações Baseadas em Conteúdo:
  ```python
  item_name = 'OPI Infinite Shine, Nail Lacquer Nail Polish, Bubble Bath'
  top_n = 5
  content_recs = content_based_recommendations(train_data, item_name, top_n)
  print(content_recs)
   ```
2. Recomendações de Filtragem Colaborativa:
  ```python
target_user_id = 4
top_n = 5
collaborative_recs = collaborative_filtering_recommendations(train_data, target_user_id, top_n)
print(collaborative_recs)
   ```
3. Recomendações Híbridas:
  ```python
target_user_id = 4
item_name = 'OPI Infinite Shine, Nail Lacquer Nail Polish, Bubble Bath'
top_n = 5
hybrid_recs = hybrid_recommendations(train_data, target_user_id, item_name, top_n)
print(hybrid_recs)
   ```
## Como Funciona
1. Recomendações Baseadas em Conteúdo:
- Utiliza as características dos produtos (tags) e vetorização TF-IDF para calcular a similaridade entre itens com base na similaridade de cosseno.

2. Filtragem Colaborativa:
- Utiliza as classificações dos usuários para calcular a similaridade entre usuários, recomendando produtos que foram bem avaliados por usuários com preferências semelhantes.

3. Sistema Híbrido:
- Combina as recomendações baseadas em conteúdo e filtragem colaborativa, removendo duplicatas para fornecer uma lista de recomendações diversificada.

