# 🖼️ Seamese networks algorithm

**Implementação de um sistema de busca por similaridade de imagens utilizando redes neurais e Triplet Loss, com foco em embeddings e análise visual no dataset MNIST.**

[![Licença](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-2.3.0-green.svg)]()
[![Status](https://img.shields.io/badge/status-concluído-greend.svg)]()
[![deploy](https://img.shields.io/badge/depoly-inactive-red.svg)]()

## 📌 Sumário

1.  [Sobre o Projeto](https://www.google.com/search?q=%23-sobre-o-projeto)
2.  [Objetivos](https://www.google.com/search?q=%23-objetivos)
3.  [Tecnologias](https://www.google.com/search?q=%23-tecnologias)
4.  [Funcionalidades](https://www.google.com/search?q=%23-funcionalidades)
5.  [Pré-requisitos](https://www.google.com/search?q=%23%25EF%25B8%258F-pr%C3%A9-requisitos)
6.  [Instalação](https://www.google.com/search?q=%23%25EF%25B8%258F-instala%C3%A7%C3%A3o)
7.  [Como utilizar](https://www.google.com/search?q=%23-como-utilizar)
8.  [Estrutura do Projeto](https://www.google.com/search?q=%23-estrutura-do-projeto)
9.  [Contribuição](https://www.google.com/search?q=%23-contribui%C3%A7%C3%A3o)
10. [Licença](https://www.google.com/search?q=%23-licen%C3%A7a)
11. [Contato](https://www.google.com/search?q=%23-contato)
12. [Recursos Adicionais](https://www.google.com/search?q=%23-recursos-adicionais)

## 💻 Sobre o Projeto

O projeto **"Busca por Similaridade de Imagens com Triplet Loss"** demonstra a construção de um sistema que aprende a representar imagens como vetores numéricos (embeddings). O objetivo é que imagens visualmente similares resultem em embeddings próximos no espaço vetorial, enquanto imagens diferentes gerem embeddings distantes. Essa abordagem é fundamental para tarefas como sistemas de recomendação de produtos, identificação de objetos e clusters de dados.

Nesta implementação, utilizamos o popular dataset **MNIST** (dígitos manuscritos) para treinar e validar o modelo. A arquitetura se baseia em uma rede neural profunda treinada com a função de perda **Triplet Loss**, que força o modelo a aprender essa relação de proximidade e distância entre embeddings.

  - *Motivação*: Proporcionar um exemplo prático e compreensível de como a Triplet Loss funciona na prática para aprendizado de embeddings em visão computacional, servindo como base para projetos mais complexos.
  - *Público-alvo*: Estudantes, pesquisadores e desenvolvedores interessados em Deep Learning, Visão Computacional e Sistemas de Recomendação.

## 🎯 Objetivos

### 🛠️ Técnicos

  - Implementar a função de perda **Triplet Loss** para treinar um modelo de embeddings.
  - Utilizar um modelo pré-treinado (**EfficientNet-B0**) como *backbone* para extração de características.
  - Desenvolver uma pipeline de dados que gere **triplets (Anchor, Positive, Negative)** a partir de um dataset de classificação.
  - Demonstrar a capacidade do modelo em encontrar **imagens similares** com base na distância entre seus embeddings.
  - Fornecer um **ambiente de execução configurável** no Google Colab, facilitando a reprodução e experimentação.

## 🚀 Tecnologias

**Núcleo do Sistema**

  - **Python**: Linguagem de programação principal.
  - **PyTorch**: Framework de Deep Learning para construção e treinamento do modelo.
  - **torchvision**: Pacote do PyTorch para datasets e transformações de visão.
  - **timm (PyTorch Image Models)**: Biblioteca para modelos pré-treinados de última geração.
  - **NumPy**: Para operações numéricas e manipulação de arrays.
  - **Pandas**: Para manipulação e análise de dados (especialmente embeddings).
  - **Matplotlib**: Para visualização de imagens e resultados.
  - **Google Colab**: Ambiente de desenvolvimento e execução.

## ✨ Funcionalidades

  - ✅ **Preparação do Ambiente**: Instalação automática de bibliotecas necessárias e configuração de parâmetros globais (`BATCH_SIZE`, `LR`, `EPOCHS`, `DEVICE`).
  - ✅ **Carregamento e Pré-processamento de Dados**: Carregamento do dataset MNIST com transformações de tensor e normalização.
  - ✅ **Geração de Triplets**: Lógica para criar amostras Triplet (Anchor, Positive, Negative) garantindo que Anchor e Positive sejam da mesma classe, e Negative seja de uma classe diferente.
  - ✅ **Modelo de Embeddings**: Utilização do **EfficientNet-B0** pré-treinado, adaptado para gerar vetores de embedding.
  - ✅ **Treinamento com Triplet Loss**: Implementação das funções de treinamento e avaliação com a `nn.TripletMarginLoss`.
  - ✅ **Salvar Melhor Modelo**: Mecanismo para salvar os pesos do modelo que apresenta a melhor performance na validação.
  - ✅ **Inferência e Busca por Similaridade**: Funções para gerar embeddings de novas imagens e encontrar as imagens mais similares em um banco de dados usando **distância euclidiana**.
  - ✅ **Visualização de Resultados**: Plotagem da imagem de consulta e das imagens mais próximas encontradas para verificação visual da similaridade.

## ⚙️ Pré-requisitos

  - **Acesso ao Google Colab**: O projeto é otimizado para execução neste ambiente.
  - **Conexão estável à internet**: Necessária para baixar bibliotecas e o dataset MNIST.
  - **Conhecimentos básicos de Python e PyTorch**: Para entender e modificar o código.

## 🛠️ Instalação

Como este projeto é idealmente executado no Google Colab, a "instalação" se resume a abrir o notebook e executar as células.

1.  **Abra o notebook no Google Colab:**
    Clique no ícone "Open in Colab" no topo deste README ou acesse diretamente o link: `https://colab.research.google.com/drive/1xJ_NOCYWMKGz7olWVlcdzYSEd4xJg5iT#scrollTo=niSSkcGm0z0K`

2.  **Execute as células:**
    Siga a ordem das seções no notebook Colab. As células contêm os comandos de instalação de bibliotecas (`!pip install...`) e todo o código-fonte necessário para o projeto.

## ❗ Como Utilizar

Após executar todas as células do notebook Google Colab:

1.  **Exploração da Configuração**: A seção "Implementando o ambiente e configurações iniciais" mostra as bibliotecas instaladas e os parâmetros definidos.
2.  **Preparação dos Dados**: As células relacionadas ao carregamento e preparação do dataset MNIST, incluindo a criação da classe `APN_MNIST_Dataset`, devem ser executadas. Você verá os tamanhos dos datasets e uma visualização de exemplo de um triplet.
3.  **Treinamento do Modelo**: A seção "Funções de Treino e Avaliação e Loop de Treinamento" iniciará o treinamento do modelo EfficientNet-B0 com a Triplet Loss. O progresso será exibido, e o melhor modelo será salvo.
4.  **Realização de Inferência**: Após o treinamento, a última seção demonstrará como gerar embeddings para um subconjunto do dataset de teste e, em seguida, buscar e visualizar as imagens mais similares a uma imagem de consulta aleatória.

### ▶️ Demonstração

*(Em breve)*

## 📂 Estrutura do Projeto

O projeto é contido principalmente em um único notebook Google Colab, estruturado em seções lógicas para facilitar a compreensão do fluxo:

```plaintext
├── seamese-network-algorithm.ipynb   # O notebook principal do Google Colab
├── LICENSE                           # LICENSE
└── README.md                         # Este arquivo
```

*(Se você tiver outros arquivos de suporte ou scripts, liste-os aqui.)*

## 🤝 Contribuição

Contribuições são bem-vindas\! Se você tiver ideias para melhorias, novas funcionalidades ou encontrar algum bug, sinta-se à vontade para:

1.  **Reportar bugs**: Abra uma [issue](https://www.google.com/search?q=https://github.com/lucasgleria/seamese-network-algorithm/issues) no GitHub.
2.  **Sugira melhorias**: Envie ideias ou *pull requests* com novas funcionalidades.
3.  **Desenvolva**:
      - Faça um *fork* do repositório.
      - Crie uma nova *branch* (`git checkout -b feature/sua-funcionalidade`).
      - Implemente suas alterações e faça os *commits*.
      - Envie um *Pull Request* detalhando suas modificações.

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](https://www.google.com/search?q=LICENSE) para mais detalhes.

## 📞 Contato & Evidências

- **Autor**: [Lucas Leria](https://github.com/lucasgleria)  
- **LinkedIn**: [lucasgleria](https://www.linkedin.com/in/lucasgleria/)  

## 🔍 Recursos Adicionais

  - [Documentação Oficial do PyTorch](https://pytorch.org/docs/stable/index.html)
  - [Documentação Oficial do timm](https://www.google.com/search?q=https://rwightman.github.io/pytorch-image-models/README/)
  - [Dataset MNIST](http://yann.lecun.com/exdb/mnist/)
