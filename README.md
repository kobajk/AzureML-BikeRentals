# Previsão de Aluguel de Bicicletas com Aprendizado Automático Automatizado (AutoML)

Este repositório contém o código e os passos necessários para treinar um modelo de regressão que prevê o número de aluguéis de bicicletas em um determinado dia. Utilizaremos o recurso de **Aprendizado Automático Automatizado** no **Azure Machine Learning** para simplificar o processo de treinamento e avaliação do modelo.

## Passo a Passo

1. **Crie um Espaço de Trabalho no Azure Machine Learning**:
    - Provisione um espaço de trabalho no Azure.
    - Use o **Azure Machine Learning Studio** para gerenciar os recursos no seu espaço de trabalho.
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/bb6eca02-4832-4e60-8940-b81b5597ae5d)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/7468735e-3ef3-433d-aa33-800ae5b9f1dd)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/133bec1a-86ce-45ef-be6b-4dd20118f6fe)


2. **Preparação dos Dados**:
    - Utilize um conjunto de dados históricos de aluguéis de bicicletas.
    - Limpe os dados, trate valores ausentes e normalize as características.
    - No caso desse treinamento, utilizamos os dados existentes em: https://aka.ms/bike-rentals

3. **Configuração do Experimento de Aprendizado Automático Automatizado**:
    - Defina as configurações do experimento, como o algoritmo de regressão, métricas de avaliação e limites de tempo.
    - Execute o experimento para treinar vários modelos com diferentes parâmetros.
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/970d72d5-5939-4ba0-bb28-a0f08295081a)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/398db64a-0400-46af-9ffc-d99d8b8300c9)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/ae73905f-9a20-47b2-992d-0d357d6e4c84)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/9d8f5ac9-afa8-481e-acb7-0108c88a313c)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/4a721410-1716-4fb8-909c-26a9e5c92ad7)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/4f1cd46f-db09-48f9-8ffb-957e3c902fbe)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/6bb2381f-74ca-45cf-b0af-455ca3128782)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/04ca615c-ae11-4d7e-bd73-92596c67d7ce)
    - 
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/830cfb86-ac50-4cdd-ac45-c3f47f75d660)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/94f1739a-f4f5-48d4-a8b8-aa59f113ec1c)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/184cd5cc-4555-413a-acb6-dab2362273db)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/7fdd03c3-4a69-4342-95a6-5ba3b7e99c02)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/947494e0-1af6-4a16-98d7-292f8c0b1bc8)
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/522e1f3c-7cad-427e-af73-fc3d237a72d1)
  
    - ![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/3b06fbe0-4346-4860-a23e-26150a96a84b)

    - Após envio seu trabalho irá passar pelo processo de configuração das execuções e após aproximadamente 15 minutor, estará concluído:


# Teste do Modelo

Verifique qual modelo foi o melhor para treinar seus dados.
![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/048c6dcb-902d-424f-9c71-6d2a300b792c)

Com isso, realize o deploy dele e depois disso estará pronto para você realizar testes no endpoint.
![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/7c1286e5-4a4c-4fe6-a47b-f2edbc1fa6b0)

Para o teste, utilizei o json abaixo:

````
{
  "input_data": {
    "columns": [
      "day",
      "mnth",
      "year",
      "season",
      "holiday",
      "weekday",
      "workingday",
      "weathersit",
      "temp",
      "atemp",
      "hum",
      "windspeed"
    ],
    "index": [0],
    "data": [[15, 7, 2024, 3, 0, 3, 1, 1, 0.8, 0.727, 0.65, 0.15]]
  }
}
````
Neste exemplo, estou enviando dados para um dia específico (15 de julho de 2024, que é uma quarta-feira no meio do verão, sem feriado, dia útil, com clima claro, temperatura de 0.8, sensação térmica de 0.727, umidade de 0.65 e velocidade do vento de 0.15).

A previsão gerada foi: 998,84

![image](https://github.com/kobajk/AzureML-BikeRentals/assets/50890222/dcfd4b13-a7d9-4494-a25f-7e4f5ce7bc3a)

