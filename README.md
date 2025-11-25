# ☀️ Solarium SIEP
## Sistema Inteligente de Estimativa de Produtividade Solar

**Projeto A3 - 2025.2**  
**Disciplina:** Sistemas de Controle e Inteligência Artificial  
**Curso:** Engenharia da Computação  
**Professor:** Noberto Maciel

---

## 📋 Descrição do Projeto

O **Solarium SIEP** é um sistema de Inteligência Artificial desenvolvido para prever a produtividade de painéis solares fotovoltaicos. O sistema combina técnicas avançadas de Machine Learning (Regressão de Séries Temporais, Grid Search) com Lógica Fuzzy para classificar a eficiência operacional dos painéis em diferentes condições climáticas.

### 🎯 Objetivo

Desenvolver um modelo preditivo capaz de:
- Prever a geração de energia solar (kWh) nas próximas 24 horas
- Classificar a eficiência do painel (Ótima, Sub-ótima, Crítica) usando Lógica Fuzzy
- Auxiliar gestores de fazendas solares na tomada de decisão e planejamento energético

---

## 👥 Equipe

- [Nome do Membro 1]
- [Nome do Membro 2]
- [Nome do Membro 3]
- [Nome do Membro 4]

---

## 🗂️ Estrutura do Repositório
```
📦 solarium-siep/
├── 📂 datasets/          # Conjuntos de dados utilizados
├── 📂 notebooks/         # Notebooks Jupyter/Colab
├── 📂 docs/             # Documentação e relatórios
├── 📂 resultados/       # Gráficos e métricas
└── 📂 referencias/      # Artigos científicos
```

---

## 🔧 Tecnologias Utilizadas

- **Linguagem:** Python 3.x
- **Plataforma:** Google Colab
- **Bibliotecas:**
  - Pandas, NumPy (manipulação de dados)
  - Scikit-learn (Machine Learning)
  - Matplotlib, Seaborn (visualização)
  - Scikit-fuzzy (Lógica Fuzzy)
  - Statsmodels (Séries Temporais)

---

## 📊 Datasets

### 1. Dados de Geração Solar
- **Fonte:** Kaggle - Solar Power Generation Data
- **Descrição:** Histórico de geração de energia (kWh) de painéis fotovoltaicos

### 2. Dados Climáticos
- **Fonte:** NASA POWER Project
- **Descrição:** Irradiação solar, temperatura ambiente e umidade

### 3. Dados Operacionais
- **Fonte:** Kaggle/UCI ML Repository
- **Descrição:** Características técnicas dos painéis (idade, eficiência nominal)

*Detalhes completos em: `/datasets/README.md`*

---

## 🤖 Metodologia

### 1. Análise Exploratória de Dados (EDA)
- Visualização de padrões temporais
- Identificação de correlações
- Detecção de outliers

### 2. Pré-processamento
- Tratamento de valores ausentes
- Normalização de features
- Engenharia de características temporais

### 3. Modelagem Preditiva
- **Regressão Linear:** Baseline
- **Random Forest:** Modelo ensemble
- **Gradient Boosting + Grid Search:** Otimização de hiperparâmetros

### 4. Sistema Fuzzy
- Classificação de eficiência baseada em:
  - Irradiação solar (Baixa/Média/Alta)
  - Temperatura do painel (Normal/Elevada/Crítica)
- Saída: Eficiência Preditiva (Ótima/Sub-ótima/Crítica)

---

## 📈 Resultados Preliminares

*[Será preenchido após a execução dos modelos]*

| Modelo              | MAE   | RMSE  | R²    |
|---------------------|-------|-------|-------|
| Regressão Linear    | -     | -     | -     |
| Random Forest       | -     | -     | -     |
| Gradient Boosting   | -     | -     | -     |

---

## 🚀 Como Executar

### Opção 1: Google Colab (Recomendado)
1. Acesse: [Notebook Principal](notebooks/Solarium_SIEP_Principal.ipynb)
2. Clique em "Open in Colab"
3. Execute as células sequencialmente

### Opção 2: Local
```bash
# Clone o repositório
git clone https://github.com/SEU_USUARIO/solarium-siep.git

# Instale as dependências
pip install -r requirements.txt

# Execute o notebook
jupyter notebook notebooks/Solarium_SIEP_Principal.ipynb
```

---

## 📚 Referências

1. [Artigo 1 - Título]
2. [Artigo 2 - Título]
3. [Artigo 3 - Título]

*Lista completa disponível em: `/docs/relatorio_final.pdf`*

---

## 📄 Licença

Este projeto foi desenvolvido para fins acadêmicos como parte da disciplina de Sistemas de Controle e Inteligência Artificial.

---

## 📞 Contato

Para dúvidas ou sugestões, entre em contato com a equipe através do GitHub Issues.

---

**Última atualização:** Novembro/2025
