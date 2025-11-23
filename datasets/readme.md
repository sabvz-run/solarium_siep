# 📊 Datasets do Solarium SIEP

Sistema Inteligente de Estimativa de Produtividade Solar

---

## ⚠️ IMPORTANTE: Acesso aos Dados

Os arquivos CSV são grandes demais para o GitHub.

**📥 Download dos Datasets:**  
Google Drive: https://drive.google.com/drive/folders/1djeVJF4Egq1vTHZ2Lkt__td-xvN0r-sW?usp=drive_link

---

## 📋 Lista de Arquivos e Renomeação

### Arquivo Original → Nome Usado no Projeto

**Dataset 1:**
- `pv.csv` → `geracao_5anos.csv`

**Dataset 2:**
- `Plant_1_Generation_Data.csv` → `plant1_geracao.csv`
- `Plant_1_Weather_Sensor_Data.csv` → `plant1_clima.csv`

**Dataset 3:**
- `POWER_Point_Hourly_[...]_UTC.csv` → `nasa_clima.csv`

**Dataset 4:**
- `pv_train_set4.csv` → `geracao_treino.csv`
- `pv_test_set4.csv` → `geracao_teste.csv`
- `weather_train_set4.csv` → `clima_treino.csv`
- `demand_train_set4.csv` → `consumo_treino.csv`
- `demand_test_set4.csv` → `consumo_teste.csv`

---

## Dataset 1: Geração Solar (5 anos)

**Arquivo:** `geracao_5anos.csv`  
**Nome original:** `pv.csv`  
**Fonte:** Kaggle - Residential Photovoltaic Power Generation  
**Link:** https://www.kaggle.com/datasets/kollosp/10kwp-5years-power-generation

**Descrição:**  
Dados de geração de energia de um sistema solar residencial de 10kWp ao longo de 5 anos (2015-2020).

**Para que serve:**
- Treinar o modelo principal de predição de geração
- Analisar sazonalidade e tendências de longo prazo
- Identificar padrões de degradação dos painéis

**Variáveis esperadas:**
- Data/hora das medições
- Energia gerada (kWh)
- Potência instantânea (kW)

**Período:** 5 anos  
**Frequência:** Horária ou diária

---

## Dataset 2: Geração e Clima de Planta Industrial

### Arquivo A: `plant1_geracao.csv`
**Nome original:** `Plant_1_Generation_Data.csv`  
**Fonte:** Kaggle - Solar Power Generation Data  
**Link:** https://www.kaggle.com/datasets/anikannal/solar-power-generation-data

**Descrição:**  
Dados de uma planta solar industrial com 22 inversores. Alta resolução temporal (15 minutos).

**Para que serve:**
- Validação cruzada do modelo
- Comparar sistema residencial vs industrial
- Análise de múltiplos inversores

**Variáveis principais:**
- `DATE_TIME`: Data e hora
- `PLANT_ID`: ID da planta
- `SOURCE_KEY`: Identificador do inversor (22 inversores)
- `DC_POWER`: Potência DC gerada (kW) - **VARIÁVEL ALVO**
- `AC_POWER`: Potência AC após inversor (kW)
- `DAILY_YIELD`: Energia diária acumulada (kWh)
- `TOTAL_YIELD`: Energia total acumulada (kWh)

**Período:** 34 dias (15 Maio - 17 Junho 2020)  
**Registros:** ~68.000 linhas  
**Frequência:** A cada 15 minutos

---

### Arquivo B: `plant1_clima.csv`
**Nome original:** `Plant_1_Weather_Sensor_Data.csv`  
**Fonte:** Kaggle - Solar Power Generation Data

**Descrição:**  
Medições dos sensores climáticos instalados na planta industrial.

**Para que serve:**
- Features (variáveis de entrada) para modelos
- Validar correlações clima-geração
- Analisar impacto da temperatura nos painéis

**Variáveis principais:**
- `DATE_TIME`: Data e hora
- `PLANT_ID`: ID da planta
- `SOURCE_KEY`: Identificador do sensor
- `AMBIENT_TEMPERATURE`: Temperatura do ar (°C)
- `MODULE_TEMPERATURE`: Temperatura da superfície do painel (°C)
- `IRRADIATION`: Irradiação solar medida no local (W/m²)

**Período:** 34 dias (Maio-Junho 2020)  
**Frequência:** A cada 15 minutos

---

## Dataset 3: Dados Climáticos Regionais (Satélite)

**Arquivo:** `nasa_clima.csv`  
**Nome original:** `POWER_Point_Hourly_20220101_20241231_012d275_038d94W_UTC.csv`  
**Fonte:** NASA POWER Project  
**Link:** https://power.larc.nasa.gov

**Descrição:**  
Dados climáticos de satélite para validação externa. Fonte científica independente.

**Para que serve:**
- Validação externa do modelo (dados não enviesados)
- Comparar dados locais vs regionais
- Benchmark com padrão científico
- Testar robustez do modelo

**Variáveis principais:**
- `YEAR`, `MO`, `DY`, `HR`: Data e hora
- `ALLSKY_SFC_SW_DWN`: Irradiação solar (kWh/m²)
- `T2M`: Temperatura a 2 metros (°C)
- `T2M_MAX`: Temperatura máxima diária (°C)
- `T2M_MIN`: Temperatura mínima diária (°C)
- `RH2M`: Umidade relativa (%)
- `WS2M`: Velocidade do vento a 2m (m/s)

**Localização:** Brasil (Lat: -12.97, Lon: -38.50)  
**Período:** 2022-2024 (3 anos)  
**Frequência:** Horária

---

## Dataset 4: Geração, Clima e Consumo (Conjunto Completo)

**Fonte:** Kaggle - Electricity Demand and Solar Generation  
**Link:** https://www.kaggle.com/datasets/pythonafroz/electricity-demand-and-solar-generation-data

**Descrição geral:**  
Conjunto de dados com geração solar, condições climáticas e demanda elétrica. Dados já divididos em treino/teste.

---

### Arquivo A: `geracao_treino.csv`
**Nome original:** `pv_train_set4.csv`

**Descrição:**  
Dados de geração solar para treinamento.

**Para que serve:**
- Treinar modelos de predição
- Análise de padrões de geração

**Variáveis esperadas:**
- Data/hora
- Geração solar (kW ou kWh)

---

### Arquivo B: `geracao_teste.csv`
**Nome original:** `pv_test_set4.csv`

**Descrição:**  
Dados de geração solar para teste.

**Para que serve:**
- Avaliar performance dos modelos
- Validação final

---

### Arquivo C: `clima_treino.csv`
**Nome original:** `weather_train_set4.csv`

**Descrição:**  
Condições climáticas para treinamento.

**Para que serve:**
- Features para modelos de predição
- Correlacionar clima com geração

**Variáveis esperadas:**
- Temperatura
- Irradiação solar
- Umidade
- Velocidade do vento

---

### Arquivo D: `consumo_treino.csv`
**Nome original:** `demand_train_set4.csv`

**Descrição:**  
Demanda elétrica residencial para treinamento.

**Para que serve:**
- Sistema de recomendações (Módulo 2)
- Calcular balanço: Geração - Consumo
- Otimizar uso de bateria

**Variáveis esperadas:**
- Data/hora
- Demanda elétrica (kW ou kWh)
- Padrão de consumo

---

### Arquivo E: `consumo_teste.csv`
**Nome original:** `demand_test_set4.csv`

**Descrição:**  
Demanda elétrica para teste.

**Para que serve:**
- Validar sistema de recomendações
- Testar balanço energético

---

## 🎯 Resumo de Utilização

| Dataset | Arquivos | Uso Principal | Módulo |
|---------|----------|---------------|--------|
| 1 | geracao_5anos.csv | Treinamento principal (5 anos) | Módulo 1 |
| 2 | plant1_geracao.csv<br>plant1_clima.csv | Validação com planta industrial | Módulo 1 |
| 3 | nasa_clima.csv | Validação externa (satélite) | Módulo 1 |
| 4 | geracao_treino.csv<br>geracao_teste.csv<br>clima_treino.csv<br>consumo_treino.csv<br>consumo_teste.csv | Sistema completo com consumo | Módulos 1 e 2 |

---

## 📈 Fluxo de Trabalho
```
DATASET 1 (5 anos)
    ↓
TREINAR MODELOS DE PREDIÇÃO
    ↓
VALIDAR com DATASET 2 (Planta Industrial)
    ↓
VALIDAR EXTERNAMENTE com DATASET 3 (NASA)
    ↓
USAR DATASET 4 (Geração + Consumo)
    ↓
IMPLEMENTAR SISTEMA DE RECOMENDAÇÕES (Módulo 2)
    ↓
TESTAR com dados de teste (Dataset 4)
```

---

## 📊 Estatísticas Gerais

**Total de arquivos:** 9 CSVs  
**Período total coberto:** 2015-2024 (~9 anos)  
**Tipos de dados:**
- ✅ Geração solar (múltiplas fontes)
- ✅ Condições climáticas (local e satélite)
- ✅ Consumo elétrico residencial
- ✅ Dados de treino e teste separados

---

## 🔗 Links Importantes

- **Kaggle (Dataset 1):** https://www.kaggle.com/datasets/kollosp/10kwp-5years-power-generation
- **Kaggle (Dataset 2):** https://www.kaggle.com/datasets/anikannal/solar-power-generation-data
- **NASA POWER (Dataset 3):** https://power.larc.nasa.gov
- **Kaggle (Dataset 4):** https://www.kaggle.com/datasets/pythonafroz/electricity-demand-and-solar-generation-data

---

**Última atualização:** Novembro 2025  
**Projeto:** Solarium SIEP - A3 2025.2  
**Disciplina:** Sistemas de Controle e Inteligência Artificial  
**Professor:** Noberto Maciel
```

---

## ✅ AÇÕES FINAIS

### 1. Renomear Arquivos

Na pasta `solarium_datasets`, renomeie:
```
pv.csv → geracao_5anos.csv

Plant_1_Generation_Data.csv → plant1_geracao.csv
Plant_1_Weather_Sensor_Data.csv → plant1_clima.csv

POWER_Point_Hourly_[...].csv → nasa_clima.csv

pv_train_set4.csv → geracao_treino.csv
pv_test_set4.csv → geracao_teste.csv
weather_train_set4.csv → clima_treino.csv
demand_train_set4.csv → consumo_treino.csv
demand_test_set4.csv → consumo_teste.csv
