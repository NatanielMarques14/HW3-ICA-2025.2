# HW3 - Análise Comparativa de Modelos de Classificação em Alta Dimensionalidade

Este repositório contém a implementação e análise do **Homework 3** da disciplina de Inteligência Computacional Aplicada (ICA - 2025.2). O trabalho foca na análise comparativa de modelos de classificação lineares e não lineares aplicados a um conjunto de dados de alta dimensionalidade.

## Autores
* **José Ferreira Lessa**
* **Victor Guedes Alves Texeira**
* **Nataniel Marques Viana Neto**
* **Matheus Rocha Gomes da Silva**

---

## Objetivo
O objetivo principal deste projeto é estabelecer relações funcionais entre variáveis preditoras e uma variável resposta ("successful" vs "unsuccessful") em um cenário de **alta dimensionalidade (252 variáveis preditoras)**. O estudo avalia o desempenho preditivo, custo computacional e o impacto da "maldição da dimensionalidade" em diferentes abordagens.

## Modelos Implementados
Foram analisados três modelos distintos, cobrindo abordagens lineares e não lineares:

1.  **Regressão Logística (Modelo Linear)**
    * **Configuração:** Regularização L2 (Ridge) com $C=1.0$.
    * **Características:** Simplicidade, interpretabilidade e eficiência computacional.
    * **Justificativa:** Ponto de partida para estabelecer uma *baseline* e verificar a separabilidade linear dos dados.

2.  **K-Nearest Neighbors (KNN - Não Linear)**
    * **Configuração:** Otimização via Grid Search ($k=\{3,5,7,11\}$) e ponderação (uniforme vs distância).
    * **Características:** Modelo baseado em instâncias (Lazy Learning).
    * **Desafio:** Alta sensibilidade à dimensionalidade do espaço de atributos.

3.  **Support Vector Machine (SVM - Não Linear)**
    * **Configuração:** Kernel RBF (Radial Basis Function) e otimização SMO.
    * **Características:** Maximização de margem e uso do *kernel trick* para fronteiras complexas.
    * **Justificativa:** Capacidade de generalização superior em espaços complexos comparado ao KNN.

## Metodologia
O pipeline de processamento dos dados seguiu as etapas abaixo:
* **Pré-processamento:** Padronização das variáveis utilizando `StandardScaler` (média zero e variância unitária).
* **Divisão dos Dados:** * Treino: 8.190 amostras.
    * Teste: 518 amostras.
* **Validação:** Validação cruzada (*k-fold cross-validation* com $k=5$) para ajuste de hiperparâmetros.
* **Métricas:** Acurácia, Matriz de Confusão, Precisão, Revocação e Especificidade.

## Resultados Obtidos

A tabela abaixo resume a acurácia obtida por cada modelo no conjunto de teste:

| Modelo | Acurácia | Observações |
| :--- | :---: | :--- |
| **Regressão Logística** | **83.98%** | Melhor desempenho geral. Bom equilíbrio entre viés e variância. |
| **SVM (Kernel RBF)** | 81.08% | Competitivo, com fronteira de decisão eficiente, mas mais complexo. |
| **KNN** | 64.00% | Desempenho inferior devido à alta dimensionalidade (*Curse of Dimensionality*). |

## Principais Conclusões
Regressão Logística: Apresentou o melhor resultado, sugerindo que a estrutura dos dados é aproximadamente linearmente separável. A regularização L2 ajudou a lidar com o grande número de variáveis.
Maldição da Dimensionalidade: O desempenho reduzido do KNN evidenciou como medidas de distância perdem poder discriminativo em espaços de alta dimensão (252 variáveis).
Robustez do SVM: Embora não tenha superado o modelo linear, o SVM mostrou-se muito mais robusto que o KNN, minimizando falsos positivos e negativos através da maximização da margem.

## Referências
Kuhn, M., & Johnson, K. (2013). Applied Predictive Modeling. Springer.
Mulas, M. (2026). Predictive Modelling Classification. Slides da disciplina, Universidade Federal do Ceará.


