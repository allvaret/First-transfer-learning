# Transfer Learning with Custom Dataset / Dataset Personalizado

## O Problema
Classificar imagens entre duas categorias — motos e carros — usando uma rede neural, com poucos dados de treino disponíveis.

## Abordagem
Em vez de treinar uma rede do zero, foi aplicada a técnica de Transfer Learning: as últimas camadas de classificação de uma rede pré-treinada foram removidas e retreinadas para o novo problema. Dessa forma, todo o aprendizado anterior da rede — armazenado nos pesos e bias das camadas anteriores — é aproveitado, economizando tempo e exigindo muito menos dados para atingir boa performance.
A confusion matrix foi usada desde o início como referência de validação, permitindo acompanhar não só a acurácia geral mas onde o modelo errava especificamente.

## Resultado

O modelo foi treinado com um subconjunto dos dados por escolha intencional de velocidade:

- **Split:** 420 treino / 90 validação / 90 teste
- **Acurácia no teste:** 95%

Após o treinamento, o modelo foi avaliado no conjunto completo de dados não utilizados:

```python
Summary of Evaluation on Unused Dataset:
  Loss: 0.1555
  Accuracy: 0.9500
  Confusion Matrix (Unused Dataset):
 [[1624   76]
 [  94 1606]]
```

95% de acurácia mantida em mais de 3.400 imagens não vistas durante o treino.

## Aprendizados
Acompanhar a variação da assertividade do modelo a cada época de treinamento tornou concreto o que antes era teórico: como os pesos se ajustam progressivamente e como isso se reflete na performance. Entender a estrutura da rede camada a camada — incluindo detalhes como a codificação dos rótulos — foi essencial para deixar de usar o modelo como caixa preta e começar a raciocinar sobre ele.

## 🚀 Funcionalidades

- Treinamento de modelos usando Transfer Learning com datasets personalizados;
- Ajuste de fine-tuning com diferentes percentuais de dados;
- Acesso interativo via Google Colab.

## 🧠 Tecnologias Utilizadas

- Python
- TensorFlow / Keras
- Google Colab
- Matplotlib / NumPy

## 🔧 Como Utilizar

1. Acesse o notebook no Colab;
2. Faça upload do seu dataset ou modifique o caminho do dataset no código;
3. Ajuste a porcentagem de imagens a serem usadas para o treinamento;
4. Execute as células para treinar e avaliar o modelo.

## ✍️ Autor

Este projeto foi desenvolvido como exercício de compreensão prática sobre Transfer Learning, com base em tutoriais educacionais.  
Modificações realizadas por: **allvaret**


---

## 📘 English Version

# Transfer Learning with Custom Dataset

This project is a fork of the original Transfer Learning / Fine-Tuning tutorial available at:  
[Colab - Transfer Learning](https://colab.research.google.com/github/kylemath/ml4a-guides/blob/master/notebooks/transfer-learning.ipynb)

This project is a fork of the original Transfer Learning / Fine Tuning tutorial available at: **[Colab - Transfer Learning](https://colab.research.google.com/github/kylemath/ml4a-guides/blob/master/notebooks/transfer-learning.ipynb)**

## The Problem

Classify images between two categories — motorcycles and cars — using a neural network with limited training data available.

## Approach

Instead of training a network from scratch, Transfer Learning was applied: the last classification layers of a pre-trained network were removed and retrained for the new problem. This way, all previous learning stored in the weights and biases of earlier layers is reused, saving time and requiring far less data to achieve strong performance. A confusion matrix was used from the start as a validation reference, allowing tracking not only of overall accuracy but where the model was specifically failing.

## Results

The model was trained on a subset of the data as an intentional speed choice:

- **Split:** 420 train / 90 validation / 90 test
- **Test accuracy:** 95%

After training, the model was evaluated on the full set of unused data:

```python
Summary of Evaluation on Unused Dataset:
  Loss: 0.1555
  Accuracy: 0.9500
  Confusion Matrix (Unused Dataset):
 [[1624   76]
 [  94 1606]]
```

95% accuracy maintained across more than 3,400 images unseen during training.

## Learnings

Watching the model's accuracy vary across each training epoch made previously theoretical concepts concrete: how weights adjust progressively and how that reflects in performance. Understanding the network's structure layer by layer — including details like label encoding — was essential to stop treating the model as a black box and start reasoning about it.

## 🚀 Features

- Model training using Transfer Learning with custom datasets
- Fine-tuning adjustment with different data percentages
- Interactive access via Google Colab

## 🧠 Technologies

- Python
- TensorFlow / Keras
- Google Colab
- Matplotlib / NumPy

## 🔧 How to Use

1. Open the notebook in Colab
2. Upload your dataset or modify the dataset path in the code
3. Adjust the percentage of images to be used for training
4. Run the cells to train and evaluate the model

## ✍️ Author

This project was developed as a practical understanding exercise on Transfer Learning, based on educational tutorials. Modifications made by: allvaret
