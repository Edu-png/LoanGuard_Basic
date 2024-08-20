# LoanGuard: Basic Decision Tree Classifier

![CAPAS - PROJETOS (4)](https://github.com/user-attachments/assets/37798ec8-47c4-4ac8-a961-f470a5687b09)

## 📋 Sumário

1. [Situação](#-situação)
2. [Objetivo](#-objetivo)
3. [Pipeline](#-pipeline)
4. [Implementação](#-implementação)
   - [Matriz de Confusão](#1-matriz-de-confusão)
   - [Curva Precision-Recall](#2-curva-precision-recall)
   - [Curva ROC](#3-curva-roc)
5. [Resultados Finais](#-resultados-finais)
6. [Conclusão](#-conclusão)
7. [Referências](#-referências)

## 🤓 Situação
Uma empresa de empréstimo de automóveis enfrenta um grande desafio devido à alta demanda para uma frota reduzida e uma elevada taxa de inadimplência dos clientes. Esses fatores estão causando prejuízos significativos. Fomos contratados para desenvolver uma solução que identifique os clientes inadimplentes antes que os empréstimos sejam concedidos, ajudando a empresa a minimizar as perdas.

## 🎯 Objetivo
Criar um modelo de classificação em Machine Learning que identifique clientes inadimplentes em uma empresa de empréstimo de automóveis, evitando prejuízos e ajudando a empresa a gerenciar melhor seus riscos.

## 🏃‍♂️ Pipeline
1. **Coleta e Pré-processamento de Dados**: Carregar os dados históricos de clientes, preparar as variáveis e dividir os dados em conjuntos de treino, validação e teste.
2. **Criação do Modelo**: Implementar um modelo de Árvore de Decisão (Decision Tree) para a classificação dos clientes.
3. **Validação do Modelo**: Usar técnicas de validação cruzada, como K-Fold, para avaliar o desempenho do modelo.
4. **Ajuste de Hiperparâmetros**: Otimizar o modelo para melhorar sua capacidade de prever clientes inadimplentes.
5. **Implementação e Avaliação Final**: Aplicar o modelo otimizado no conjunto de teste e avaliar seu desempenho utilizando métricas como matriz de confusão, curva ROC, e precisão vs. recall.

## 🚀 Implementação

### 1. Matriz de Confusão
A matriz de confusão revela que, embora o modelo tenha um bom desempenho ao identificar clientes adimplentes (com apenas 116 falsos positivos), ele tem uma baixa capacidade de identificar clientes inadimplentes. Dos 960 casos de inadimplência, o modelo identificou corretamente apenas 42, subestimando assim a quantidade de clientes que não pagariam o empréstimo.

![Confusion_matrix](https://github.com/user-attachments/assets/cd8186ee-afb5-4bc7-8c44-27b1be8856ac)

### 2. Curva Precision-Recall
A curva Precision-Recall demonstra o desempenho da Árvore de Decisão na detecção de clientes inadimplentes. A precisão cai rapidamente para valores muito baixos conforme o recall aumenta, sugerindo que o modelo não é eficaz em identificar corretamente os clientes inadimplentes sem gerar muitos falsos positivos.

![curva_precision_recall](https://github.com/user-attachments/assets/255f2b3c-f12c-4050-a666-20c7346dd617)

### 3. Curva ROC
A curva ROC indica que o modelo de Árvore de Decisão tem uma capacidade de discriminação entre as classes positiva e negativa quase aleatória, com um valor de AUC de 0,52. Isso mostra que o modelo não está diferenciando bem entre os clientes adimplentes e inadimplentes.

![curva_roc](https://github.com/user-attachments/assets/a8e0994a-310f-4439-b932-87168840e769)

## 📈 Resultados Finais
O modelo final, após ajustes e validação cruzada, apresentou os seguintes resultados ao ser aplicado no conjunto de teste:

- **Acurácia Geral**: 50%
- **Precisão (Classe 0 - Adimplente)**: 94%
- **Recall (Classe 0 - Adimplente)**: 48%
- **Precisão (Classe 1 - Inadimplente)**: 11%
- **Recall (Classe 1 - Inadimplente)**: 70%

Apesar de a acurácia geral ser baixa, o modelo conseguiu capturar uma parte significativa dos inadimplentes (recall de 70%), embora com muitos falsos positivos.

![matrix_final](https://github.com/user-attachments/assets/d36f0073-bfd8-4c57-a018-48b5e07aac77)


## 📝 Conclusão
O modelo de Árvore de Decisão desenvolvido para identificar clientes inadimplentes ainda apresenta limitações, especialmente no equilíbrio entre precisão e recall. O alto número de falsos positivos e a baixa precisão na detecção de inadimplentes sugerem a necessidade de mais ajustes, como a utilização de técnicas de balanceamento de dados (Oversampling/Undersampling) e a experimentação com outros algoritmos de Machine Learning. Esses ajustes são essenciais para tornar o modelo mais eficaz e reduzir os riscos financeiros para a empresa.

## 📚 Referências
- [Documentação do Scikit-learn](https://scikit-learn.org/stable/documentation.html)
- [Guia de Oversampling e Undersampling com SMOTE e NearMiss](https://imbalanced-learn.org/stable/)
- [Introdução ao Machine Learning](https://www.coursera.org/learn/machine-learning)
