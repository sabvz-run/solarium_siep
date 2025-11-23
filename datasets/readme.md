<div align="center">

# Datasets do Solarium SIEP
**Sistema Inteligente de Estimativa de Produtividade Solar**
</div>

<br>

## Acesso aos Dados
Os arquivos CSV estão disponíveis acima, mas são grandes demais para serem visualizados diretamente no GitHub. 
É possível fazer o download dos [Solarium Datasets](https://drive.google.com/drive/folders/1l6wwwaX-AVYbF-ELtKQSfro4AYuFzikx) pelo Google Drive clicando no hiperlink.

<br>

---

## Dataset 1: Geração Solar Residencial (5 anos)
<img align="right" src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Sun%20Behind%20Cloud.png" width="120" />

<details>
<summary><b>Ver detalhes de geracao_5anos.csv</b></summary>

<br>

**Arquivo:** `geracao_5anos.csv`  
**Original:** `pv.csv`  
**Fonte:** [Kaggle - Residential PV Power Generation](https://www.kaggle.com/datasets/kollosp/10kwp-5years-power-generation)  
**Período:** 2015-2020 (5 anos)  
**Frequência:** Horária/Diária  
**Sistema:** 10kWp residencial

### Descrição
Dados de geração de energia de um sistema solar residencial ao longo de 5 anos, cobrindo ciclos sazonais completos.

### Para que serve
- Treinar o modelo principal de predição de geração
- Analisar sazonalidade e tendências de longo prazo
- Identificar padrões de degradação dos painéis

### Variáveis
- `datetime` - Data e hora das medições
- `energy_kwh` - Energia gerada (kWh)
- `power_kw` - Potência instantânea (kW)

### Uso no Projeto
**Módulo 1** - Treinamento Principal

</details>

<br clear="right"/>

---

## Dataset 2: Geração e Clima de Planta Industrial
<img align="right" src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/High%20Voltage.png" width="120" />

### Dataset 2A: Geração

<details>
<summary><b>Ver detalhes de plant1_geracao.csv</b></summary>

<br>

**Arquivo:** `plant1_geracao.csv`  
**Original:** `Plant_1_Generation_Data.csv`  
**Fonte:** [Kaggle - Solar Power Generation Data](https://www.kaggle.com/datasets/anikannal/solar-power-generation-data)  
**Período:** 34 dias (15 Mai - 17 Jun 2020)  
**Registros:** ~68.000 linhas  
**Frequência:** A cada 15 minutos  
**Inversores:** 22 unidades

### Descrição
Dados de uma planta solar industrial com múltiplos inversores, oferecendo alta resolução temporal.

### Para que serve
- Validação cruzada do modelo
- Comparar sistema residencial vs industrial
- Análise de desempenho de múltiplos inversores

### Variáveis
- `DATE_TIME` - Data e hora
- `PLANT_ID` - ID da planta
- `SOURCE_KEY` - Identificador do inversor (1-22)
- `DC_POWER` - Potência DC gerada (kW) **[VARIÁVEL ALVO]**
- `AC_POWER` - Potência AC após inversor (kW)
- `DAILY_YIELD` - Energia diária acumulada (kWh)
- `TOTAL_YIELD` - Energia total acumulada (kWh)

### Uso no Projeto
**Módulo 1** - Validação Cruzada

</details>

### Dataset 2B: Clima

<details>
<summary><b>Ver detalhes de plant1_clima.csv</b></summary>

<br>

**Arquivo:** `plant1_clima.csv`  
**Original:** `Plant_1_Weather_Sensor_Data.csv`  
**Fonte:** [Kaggle - Solar Power Generation Data](https://www.kaggle.com/datasets/anikannal/solar-power-generation-data)  
**Período:** 34 dias (Mai-Jun 2020)  
**Frequência:** A cada 15 minutos

### Descrição
Medições dos sensores climáticos instalados na planta, sincronizadas com os dados de geração.

### Para que serve
- Features (entrada) para modelos de predição
- Validar correlações clima-geração
- Analisar impacto da temperatura nos painéis

### Variáveis
- `DATE_TIME` - Data e hora
- `PLANT_ID` - ID da planta
- `SOURCE_KEY` - Identificador do sensor
- `AMBIENT_TEMPERATURE` - Temperatura do ar (°C)
- `MODULE_TEMPERATURE` - Temperatura da superfície do painel (°C)
- `IRRADIATION` - Irradiação solar medida (W/m²)

### Uso no Projeto
**Módulo 1** - Features para Predição

</details>

<br clear="right"/>

---

## Dataset 3: Dados Climáticos Regionais (Satélite NASA)
<img align="right" src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Travel%20and%20places/Sun%20Behind%20Small%20Cloud.png" width="120" />

<details>
<summary><b>Ver detalhes de nasa_clima.csv</b></summary>

<br>

**Arquivo:** `nasa_clima.csv`  
**Original:** `POWER_Point_Hourly_20220101_20241231_012d275_038d94W_UTC.csv`  
**Fonte:** [NASA POWER Project](https://power.larc.nasa.gov)  
**Localização:** Brasil (Lat: -12.97, Lon: -38.50)  
**Período:** 2022-2024 (3 anos)  
**Frequência:** Horária

### Descrição
Dados climáticos de satélite para validação externa, oferecendo fonte científica independente e não enviesada.

### Para que serve
- Validação externa do modelo (dados não enviesados)
- Comparar dados locais vs regionais
- Benchmark com padrão científico
- Testar robustez do modelo

### Variáveis
- `YEAR`, `MO`, `DY`, `HR` - Data e hora
- `ALLSKY_SFC_SW_DWN` - Irradiação solar (kWh/m²)
- `T2M` - Temperatura a 2 metros (°C)
- `T2M_MAX` / `T2M_MIN` - Temperatura máxima/mínima diária (°C)
- `RH2M` - Umidade relativa (%)
- `WS2M` - Velocidade do vento a 2m (m/s)

### Uso no Projeto
**Módulo 1** - Validação Externa

</details>

<br clear="right"/>

---

## Dataset 4: Conjunto Completo (Geração + Clima + Consumo)
<img align="right" src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Battery.png" width="120" />

**Fonte:** [Kaggle - Electricity Demand and Solar Generation](https://www.kaggle.com/datasets/pythonafroz/electricity-demand-and-solar-generation-data)

Conjunto integrado com geração solar, condições climáticas e demanda elétrica. Dados pré-divididos em treino/teste.

### 4A: Geração (Treino)

<details>
<summary><b>Ver detalhes de geracao_treino.csv</b></summary>

<br>

**Original:** `pv_train_set4.csv`  
**Uso:** Treinar modelos de predição de geração solar  
**Variáveis:** Data/hora, Geração solar (kW/kWh)  
**Módulo:** 1

</details>

### 4B: Geração (Teste)

<details>
<summary><b>Ver detalhes de geracao_teste.csv</b></summary>

<br>

**Original:** `pv_test_set4.csv`  
**Uso:** Avaliar performance dos modelos (validação final)  
**Variáveis:** Data/hora, Geração solar (kW/kWh)  
**Módulo:** 1

</details>

### 4C: Clima (Treino)

<details>
<summary><b>Ver detalhes de clima_treino.csv</b></summary>

<br>

**Original:** `weather_train_set4.csv`  
**Uso:** Features para modelos (temperatura, irradiação, umidade, vento)  
**Função:** Correlacionar clima com geração  
**Módulo:** 1

</details>

### 4D: Consumo (Treino)

<details>
<summary><b>Ver detalhes de consumo_treino.csv</b></summary>

<br>

**Original:** `demand_train_set4.csv`  
**Uso:** Sistema de recomendações  
**Função:** Calcular balanço (Geração - Consumo), otimizar bateria  
**Módulo:** 2

</details>

### 4E: Consumo (Teste)

<details>
<summary><b>Ver detalhes de consumo_teste.csv</b></summary>

<br>

**Original:** `demand_test_set4.csv`  
**Uso:** Validar sistema de recomendações e balanço energético  
**Módulo:** 2

</details>

<br clear="right"/>

---

## Visão Geral

### Resumo de Utilização

**Dataset 1** - `geracao_5anos.csv`  
→ Treinamento principal (5 anos) | Módulo 1

**Dataset 2** - `plant1_geracao.csv` + `plant1_clima.csv`  
→ Validação com planta industrial | Módulo 1

**Dataset 3** - `nasa_clima.csv`  
→ Validação externa (satélite) | Módulo 1

**Dataset 4** - 5 arquivos (geração, clima, consumo)  
→ Sistema completo com recomendações | Módulos 1 e 2

### Estatísticas Gerais

- **Total de arquivos:** 9 CSVs
- **Período coberto:** 2015-2024 (~9 anos)
- **Tipos de dados:** Geração solar, Condições climáticas, Consumo elétrico
- **Organização:** Treino/teste separados

<br>

## Fluxo de Trabalho

```
┌─────────────────────────────────────────────────────────────┐
│  DATASET 1 (5 anos)                                         │
│  └─> Treinar Modelos de Predição                           │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│  DATASET 2 (Planta Industrial)                              │
│  └─> Validação Cruzada                                      │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│  DATASET 3 (NASA)                                           │
│  └─> Validação Externa                                      │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│  DATASET 4 (Geração + Consumo)                              │
│  └─> Sistema de Recomendações (Módulo 2)                   │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│  TESTE FINAL                                                │
│  └─> Avaliação com Dados de Teste                          │
└─────────────────────────────────────────────────────────────┘
```

<br>

---

<div align="center">

**Projeto:** Solarium SIEP - A3 2025.2  
**Disciplina:** Sistemas de Controle e Inteligência Artificial  
**Professor:** Noberto Maciel

</div>
