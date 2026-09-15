
# 🔍 Inspeção Automatizada de Peças de Fundição Metalúrgica

**Disciplina:** Machine Learning e Visão Computacional
**Contexto:** Indústria 4.0

Este projeto desenvolve um sistema de inspeção automatizada para peças de fundição metalúrgica, utilizando técnicas de Visão Computacional e Machine Learning. O objetivo principal é identificar defeitos em peças de forma autônoma, otimizando o controle de qualidade e a eficiência da produção no cenário da Indústria 4.0.

## 🛠️ Tecnologias Utilizadas

| Tecnologia          | Descrição                                                                      |
| :------------------ | :----------------------------------------------------------------------------- |
| **Python**          | Linguagem de programação principal para desenvolvimento e prototipagem.        |
| **OpenCV**          | Biblioteca para processamento de imagens e visão computacional clássica.       |
| **TensorFlow/Keras**| Framework para construção e treinamento de Redes Neurais Convolucionais (CNNs).|
| **Scikit-Learn**    | Ferramentas para métricas de avaliação e pré-processamento de dados.          |
| **Matplotlib**      | Geração de gráficos e visualização de dados.                                   |
| **Git/GitHub**      | Controle de versão do código, colaboração e gestão de issues.                  |

## 🗺️ Mapeamento das Sprints e Issues Industriais

O projeto foi estruturado em 6 Sprints, com um total de 12 Issues desenvolvidas, seguindo uma abordagem ágil:

*   **Sprint 1: Configuração e Versionamento**
    *   **Issue #1:** Configuração do ambiente de desenvolvimento (Google Colab).
    *   **Issue #2:** Download e organização do dataset de peças de fundição.
    *   **Issue #3:** Inicialização do controle de versão com Git/GitHub.

*   **Sprint 2: Análise Exploratória Clássica (OpenCV)**
    *   **Issue #4:** Carregamento, visualização e conversão para escala de cinza de imagens de amostra.

*   **Sprint 3: Destaque de Características**
    *   **Issue #5:** Aplicação de filtros de suavização (Gaussian Blur, Median Blur).
    *   **Issue #6:** Implementação da detecção de bordas (Canny, Sobel).
    *   **Issue #7:** Realização de limiarização (Otsu) e operações morfológicas (Erosão, Dilatação).

*   **Sprint 4: Ingestão de Dados e Augmentation (Keras)**
    *   **Issue #8:** Preparação do dataset para treinamento de redes neurais.
    *   **Issue #9:** Configuração de `ImageDataGenerator` para aumento de dados (Data Augmentation) e criação de geradores de treino e validação.

*   **Sprint 5: A Arquitetura CNN e Treinamento**
    *   **Issue #10:** Definição, construção, compilação e treinamento de uma arquitetura de Rede Neural Convolucional (CNN).

*   **Sprint 6: Auditoria e Gravação**
    *   **Issue #11:** Avaliação do modelo treinado com métricas de desempenho e geração de gráficos de acurácia e perda.
    *   **Issue #12:** Análise diagnóstica detalhada da Rede Neural Convolucional (CNN), identificação de overfitting, e salvamento do melhor modelo.

## 📊 Resultados e Avaliação

### Visão Computacional Clássica (OpenCV)

As técnicas de processamento de imagem com OpenCV foram cruciais para a fase de pré-análise e destaque de características das peças. A aplicação de filtros de suavização (Gaussian, Median) reduziu ruídos, enquanto a limiarização de Otsu e os detectores de bordas (Canny, Sobel) permitiram realçar regiões de interesse e potenciais defeitos. Operações morfológicas como Erosão e Dilatação refinaram essas características, preparando as imagens para a detecção de padrões ou para servir como entrada para modelos de Machine Learning.

### Rede Neural Convolucional (CNN)

O modelo de Rede Neural Convolucional desenvolvido demonstrou uma boa capacidade de classificação. Após o treinamento, o modelo alcançou uma **acurácia de validação de aproximadamente 91.89%** e uma **perda de validação de 0.1860** na melhor época (Época 35). A análise diagnóstica, realizada na **Issue #12**, revelou:

- O menor `val_loss` foi alcançado na época 35 com o valor: 0.1860.
- Foram detectados **potenciais sinais de Overfitting**, onde o `loss` de treino continuou caindo (de 0.2795 para 0.2386), enquanto o `val_loss` começou a aumentar (de 0.1860 para 0.1970) após a época 35. Isso sugere que o modelo pode estar memorizando dados de treino em vez de generalizar para novos dados. A adição de regularização L2 e Dropout ajudou a mitigar esse efeito, mas a vigilância ainda é necessária.

O relatório de classificação detalhou as métricas para cada classe (`def_front` e `ok_front`), com precisão e recall balanceados, e a matriz de confusão visualizou a performance da classificação, mostrando a distribuição de acertos e erros do modelo.

## 🚀 Como Executar no Google Colab

Para executar este notebook no Google Colab e aproveitar o suporte a GPU T4, siga os passos abaixo:

1.  **Abrir no Google Colab:** Clique no botão "Open in Colab" (ou carregue o arquivo `.ipynb` diretamente).
2.  **Configurar Aceleração por Hardware:**
    *   No menu superior, vá em `Ambiente de execução` (Runtime).
    *   Selecione `Alterar tipo de ambiente de execução` (Change runtime type).
    *   Em "Tipo de ambiente de execução", escolha `Python 3`.
    *   Em "Acelerador de hardware", selecione `GPU`.
    *   Clique em `Salvar`.
3.  **Executar as Células:** Execute as células do notebook sequencialmente, clicando no botão "Play" ao lado de cada célula ou usando `Ctrl+Enter` (para executar a célula atual) ou `Ctrl+F9` (para executar todas as células).
4.  **Acompanhar o Progresso:** Observe a saída das células para monitorar o download de dados, o treinamento do modelo e a geração de gráficos e relatórios.

## 🎥 Vídeo de Demonstração Técnica

Um vídeo demonstrativo técnico (máximo 5 minutos), hospedado no Google Drive, está disponível para ilustrar o funcionamento do sistema e os resultados obtidos.

[**Link para o Vídeo de Demonstração**](https://drive.google.com/link/para/o/seu/video/aqui) (placeholder: Por favor, insira o URL do seu vídeo aqui)

## 📝 Padrão de Versionamento

Este projeto adota o padrão de versionamento [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), que estabelece um conjunto de regras para a criação de mensagens de commit claras e informativas. Isso facilita o rastreamento de mudanças, a geração automatizada de changelogs e a compreensão do histórico do projeto.

**Exemplos de commits:**

*   `feat: Adiciona módulo de detecção de bordas Canny (#6)`
*   `fix: Corrige erro na leitura de imagens grayscale (#4)`
*   `docs: Atualiza seção de resultados no README.md (#12)`
*   `refactor: Otimiza função de pré-processamento de imagens (#7)`

**Autor:**

*   [Seu Nome / Nome da Equipe]

```
