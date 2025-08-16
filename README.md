# Reconhecimento de Dígitos Manuscritos (MNIST)

Este projeto é uma aplicação em **Python + Flask** que utiliza um modelo de **rede neural treinado no dataset MNIST** para reconhecer dígitos manuscritos a partir de imagens enviadas pelo usuário.

## 🧠 Como funciona

1. O modelo é treinado em `treinar_modelo.py` usando a base **MNIST** (imagens de dígitos de 0 a 9).  
   - Modelo simples: camada `Flatten`, `Dense(128, relu)` e `Dense(10, softmax)`.  
   - Após o treino, o modelo é salvo em `modelo_mnist.h5`.  

2. A aplicação Flask (`app.py`) carrega esse modelo e disponibiliza uma interface web:  
   - O usuário envia uma imagem com um dígito escrito à mão.  
   - A imagem é pré-processada (`28x28 px`, escala de cinza, normalizada).  
   - O modelo faz a **predição** e retorna o número reconhecido em JSON.  

3. Scripts auxiliares:  
   - `salvar_imagens_mnist.py`: salva algumas imagens do dataset MNIST para visualização.  
   - `appteste.py`: realiza testes rápidos com o modelo já treinado.  

## 📂 Estrutura do Projeto

projeto-Si-main/

│── app.py # Aplicação Flask (backend principal)

│── appteste.py # Script de teste do modelo

│── treinar_modelo.py # Treinamento do modelo MNIST

│── salvar_imagens_mnist.py # Exporta imagens do dataset

│── modelo_mnist.h5 # Modelo treinado salvo

│── requirements.txt # Dependências do projeto

│── static/ # Imagens processadas e arquivos estáticos

│── templates/ # Páginas HTML (index.html)


## 🔧 Requisitos

O projeto usa **Python 3.12** e as seguintes bibliotecas:

- Flask  
- TensorFlow  
- NumPy  
- Pillow  
- Scikit-learn  
- Joblib  

Instale tudo com:

```bash
pip install -r requirements.txt
▶️ Executando o projeto
Treine o modelo (opcional, já existe um salvo em modelo_mnist.h5):

bash
python treinar_modelo.py

Inicie a aplicação Flask:
bash
python app.py

Acesse no navegador:
http://127.0.0.1:5000
