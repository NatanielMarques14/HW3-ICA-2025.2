# HW3 - Análise Comparativa de Modelos de Classificação em Alta Dimensionalidade

Este repositório contém a implementação e análise do **Homework 3** da disciplina de Inteligência Computacional Aplicada (ICA - 2025.2). O trabalho foca na análise comparativa de modelos de classificação lineares e não lineares aplicados a um conjunto de dados de alta dimensionalidade.

## 👥 Autores
* **José Ferreira Lessa**
* **Victor Guedes Alves Texeira**
* **Nataniel Marques Viana Neto**
* **Matheus Rocha Gomes da Silva**

---

## 🎯 Objetivo
O objetivo principal deste projeto é estabelecer relações funcionais entre variáveis preditoras e uma variável resposta ("successful" vs "unsuccessful") em um cenário de **alta dimensionalidade (252 variáveis preditoras)**. O estudo avalia o desempenho preditivo, custo computacional e o impacto da "maldição da dimensionalidade" em diferentes abordagens.

## 🧠 Modelos Implementados
Foram analisados três modelos distintos, cobrindo abordagens lineares e não lineares:

1.  **Regressão Logística (Modelo Linear)**
    * **Configuração:** Regularização L2 (Ridge) com $C=1.0$.
    * **Características:** Simplicidade, interpretabilidade e eficiência computacional.
    * **Justificativa:** Ponto de partida para estabelecer uma *baseline* e verificar a separabilidade linear dos dados.

2.  **K-Nearest Neighbors (KNN - Não Linear)**
    * **Configuração:** Otimização via Grid Search ($k=\{3,5,7,11\}$) e ponderação (uniforme vs distância).
    * **Características:** Modelo baseado em instâncias (Lazy Learning).
    * **Desafio:** Alta sensibilidade à dimensionalidade do espaço de atributos.

3.  **
