# MlpCnnClassifier

Este projeto apresenta uma análise comparativa entre duas arquiteturas fundamentais de Redes Neurais — MLP (Multi-Layer Perceptron) e CNN (Convolutional Neural Networks) — aplicadas à tarefa de classificação de imagens utilizando o dataset CIFAR-10 e o framework PyTorch.

O projeto consiste em uma análise comparativa de diferentes arquiteturas de redes neurais para uma tarefa de classificação de imagens multiclasse. O dataset utilizado é o CIFAR-10, composto por um conjunto de 60.000 imagens coloridas de 32x32 pixels, e 10 classes de saída que abrangem categorias de animais e veículos. O objetivo é avaliar o desempenho e a capacidade de extração de características de modelos MLP frente a modelos CNN.

## Dataset: CIFAR-10

O CIFAR-10 é um conjunto de dados padrão para algoritmos de visão computacional e aprendizado de máquina, dividido em:
* 50.000 imagens para treinamento.
* 10.000 imagens para teste.
* Classes: avião, automóvel, pássaro, gato, veado, cão, sapo, cavalo, navio e caminhão.

## Roadmap de Pré-processamento

Para garantir a eficiência dos modelos, o pipeline de dados seguiu as seguintes etapas técnicas:

### 1. Configuração do Ambiente
Uso da biblioteca `torchvision` para a gestão automatizada de datasets e verificação de disponibilidade do `cuda` (GPU) para aceleração do processamento tensorial.

### 2. Normalização
Conversão dos valores de intensidade de pixels (originalmente entre 0 e 255) para Tensores no intervalo [0, 1]. Esta etapa é crucial para a estabilidade numérica do gradiente durante o backpropagation.

### 3. Data Loading
Implementação de `DataLoaders` com os seguintes parâmetros:
* **Batch Size:** 64 imagens por lote.
* **Shuffle:** Habilitado para os dados de treino para evitar viés de ordem durante as épocas.
* **Num Workers:** Configuração para carregamento paralelo de dados.

## Arquiteturas Implementadas

### MLP (Multi-Layer Perceptron)
Rede neural totalmente conectada onde os dados espaciais da imagem (32x32x3) são transformados em um vetor unidimensional de 3072 elementos na entrada.

### CNN (Convolutional Neural Network)
Rede que preserva a hierarquia espacial através de camadas de convolução e pooling, permitindo a extração de padrões como bordas e texturas antes das camadas de decisão final.


## Tecnologias Utilizadas
* Python 3.x
* PyTorch
* Torchvision
* Matplotlib
* NumPy
