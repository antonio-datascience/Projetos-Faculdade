<!-- HEADER SECTION -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=140&color=gradient&customColorList=30,30,30&text=Antonio%20•%20Data%20Scientist&section=header&reversal=false&fontAlign=50&fontSize=35&fontColor=000000&textBg=false" />
# 🧹 Preparação e Transformação dos Dados

**Autor:** Antonio Paulo  
**Instituição:** UniCEUB – Centro Universitário de Brasília  
**Licença:** Creative Commons  
**GitHub:** [@antonio-datascience](https://github.com/antonio-datascience)  

---

## 🎯 Objetivo do Projeto

Este projeto tem como objetivo demonstrar as etapas fundamentais de **preparação e transformação de dados** em um processo de **Ciência de Dados**, utilizando a linguagem **Python** e as bibliotecas **Pandas** e **Matplotlib**.

A limpeza e transformação dos dados são etapas cruciais para garantir a **qualidade e confiabilidade** dos resultados em modelos de análise e aprendizado de máquina.

---

## 📊 Conjunto de Dados

O dataset utilizado é o **California Housing Dataset**, disponível no Google Colab (`/content/sample_data/california_housing_train.csv`).  
Ele contém informações sobre habitações na Califórnia, incluindo variáveis como:

- `longitude` e `latitude`  
- `housing_median_age`  
- `total_rooms`, `total_bedrooms`  
- `population`, `households`  
- `median_income`  
- `median_house_value`  

---

## ⚙️ Etapas do Projeto

### 1. Importação das Bibliotecas

```python
import random
import pandas as pd
import matplotlib.pyplot as plt

random.seed(1)
data = pd.read_csv('/content/sample_data/california_housing_train.csv', header=0)
print("Número de linhas e colunas:", data.shape)
```

### 2. Tratamento de Valores Ausentes

Remoção de linhas com valores `NaN` (Not a Number), que representam dados ausentes ou corrompidos.

```python
data = data.dropna()
print(data.shape)
```

➡️ **Resultado:** Linhas com valores ausentes foram removidas com sucesso, reduzindo o número total de registros.

---

### 3. Identificação e Remoção de Duplicatas

Verificação de registros duplicados e exclusão para evitar distorções nas análises.

```python
data.duplicated()
data = data.drop_duplicates()
```

➡️ **Resultado:** Registros duplicados foram eliminados. O dataset agora contém apenas entradas únicas.

---

### 4. Padronização de Dados Inválidos

Conversão de valores inconsistentes (como `"?"` ou strings incorretas) para `NaN`, seguida de nova limpeza:

```python
data.replace("?", pd.NA, inplace=True)
data = data.dropna()
```

➡️ **Resultado:** O conjunto de dados ficou completamente limpo e padronizado, sem caracteres inválidos.

---

### 5. Transformações e Pré-processamento

Aplicação de técnicas básicas de transformação de dados, como **normalização**, **padronização** e **análise estatística** preliminar.

Exemplo:

```python
# Estatísticas descritivas
data.describe()

# Normalização de colunas
data['median_income'] = (data['median_income'] - data['median_income'].min()) / (data['median_income'].max() - data['median_income'].min())
```

---

### 6. Visualização dos Dados

Criação de gráficos para inspeção visual e detecção de padrões ou outliers:

```python
plt.figure(figsize=(8,6))
plt.hist(data['median_house_value'], bins=50)
plt.title('Distribuição dos Valores das Casas na Califórnia')
plt.xlabel('Valor Mediano')
plt.ylabel('Frequência')
plt.show()
```

➡️ **Resultado:** O gráfico revelou uma distribuição assimétrica, com predominância de valores medianos abaixo de 200.000, indicando desigualdade habitacional.

---

## 📈 Resultados e Conclusões

- Todas as **linhas duplicadas e ausentes** foram corretamente removidas.  
- As **colunas numéricas foram normalizadas**, permitindo análises estatísticas consistentes.  
- As **visualizações evidenciaram padrões** importantes nos dados de habitação da Califórnia.  
- O dataset final está pronto para ser utilizado em etapas subsequentes de **modelagem e predição**.

---

## 🧠 Tecnologias Utilizadas

| Categoria | Ferramenta |
|------------|-------------|
| Linguagem  | Python |
| Bibliotecas | Pandas, Matplotlib |
| Ambiente | Google Colab |
| Dataset | California Housing Dataset |

---

## 📘 Conclusão Geral

Este projeto demonstrou a importância da **preparação e transformação de dados** como parte essencial do pipeline de ciência de dados.  
A limpeza, padronização e análise inicial de dados garantem maior **confiabilidade, precisão e eficiência** em análises futuras.

---

## 📂 Estrutura Recomendada no GitHub

```
├── Preparação_e_transformação_dos_dados.ipynb
├── README.md
├── data/
│   └── california_housing_train.csv
└── imgs/
    └── histograma_valor_medio.png
```
</div>
<!-- FOOTER WAVE -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=140&color=gradient&customColorList=30,30,30&reversal=true&section=footer" />
