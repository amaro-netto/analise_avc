# 🩺 PREVISÃO DE ACIDENTE VASCULAR CEREBRAL (AVC)

![Python: 3.9+](https://img.shields.io/badge/Python-3.9+-3776AB?labelColor=171717&style=for-the-badge&logo=python&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-F37626?labelColor=171717&style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?labelColor=171717&style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?labelColor=171717&style=for-the-badge&logo=scikit-learn&logoColor=white)
![Status](https://img.shields.io/badge/STATUS-Conclu%C3%ADdo-4CAF50?style=for-the-badge)

---

### **Índice**
- [**Índice**](#índice)
- [📝 **Descrição do Projeto**](#-descrição-do-projeto)
- [⚙️ **Tecnologias Utilizadas**](#️-tecnologias-utilizadas)
- [📁 **Estrutura do Projeto**](#-estrutura-do-projeto)
- [\*\* Fluxo de Funcionamento\*\*](#-fluxo-de-funcionamento)
- [**Principais Funcionalidades**](#principais-funcionalidades)
- [**Como funciona**](#como-funciona)
- [👥 **Equipe do Projeto**](#-equipe-do-projeto)
- [✅ **Conclusão e Insights**](#-conclusão-e-insights)

---

### 📝 **Descrição do Projeto**

Este projeto de **Machine Learning** tem como objetivo construir e implementar um modelo de classificação capaz de prever a probabilidade de um paciente sofrer um Acidente Vascular Cerebral (AVC). O modelo foi desenvolvido para auxiliar organizações de saúde na identificação proativa de pacientes de alto risco, permitindo intervenções clínicas e preventivas precoces. O foco foi em construir um modelo clinicamente validado, com ênfase nas métricas de **Sensibilidade (Recall)** e **AUC**.

#### ⚙️ **Tecnologias Utilizadas**

* **Linguagem:** Python
* **Ambiente:** Jupyter Notebook
* **Bibliotecas Principais:**
    * **Pandas:** Manipulação e limpeza de dados.
    * **NumPy:** Operações numéricas.
    * **Scikit-learn:** Particionamento, Pré-processamento (Pipeline) e Modelos (Regressão Logística, Random Forest).
    * **XGBoost:** Modelo de *boosting* de alto desempenho.
    * **Imbalanced-learn:** Implementação da técnica SMOTE para balanceamento de classes.
    * **Matplotlib/Seaborn:** Análise Exploratória de Dados (EDA).

#### 📁 **Estrutura do Projeto**
```
analise_avc/
├── data/
│   └── healthcare-dataset-stroke-data.csv  # Dados originais
├── output/
│   ├── [modelo_campeao]_stroke_model.joblib # Modelo final salvo
│   └── preprocessor.joblib                # Pré-processador Pipeline salvo
├── scripts/
│   └── stroke_prediction.ipynb             # Notebook principal com a análise
└── requirements.txt                        # Lista de dependências do ambiente virtual
```
#### ** Fluxo de Funcionamento**
```mermaid
graph TD
    A[Carregar_Dados_CSV] --> B{Limpeza_e_Imputacao};
    B --> C[Analise_Exploratoria_EDA];
    C --> D{Particionamento_Treino_Teste};
    D --> E[Balanceamento_SMOTE];
    E --> F(Treinamento_de_Modelos);
    F --> G(Avaliacao_AUC_Sensibilidade);
    G --> H[Selecao_do_Melhor_Modelo];
    H --> I(Deploy_Simulacao_Previsao);
```
### 🚀 **Funcionalidades e Demonstração**

#### **Principais Funcionalidades**
1.  **Limpeza e Imputação:** Tratamento de valores ausentes (`imc` preenchido com a mediana).
2.  **Tratamento de Desequilíbrio:** Utilização de **SMOTE** no conjunto de treino para aumentar a detecção de casos de AVC.
3.  **Modelagem Abrangente:** Comparação de modelos lineares (Regressão Logística) e complexos (Random Forest, XGBoost).
4.  **Validação Rigorosa:** Avaliação baseada em **Sensibilidade (Recall)** e **AUC** para garantir a eficácia clínica.
5.  **Implementação Pronta:** Salvamento do modelo e do pré-processador via `joblib` para deploy imediato.

#### **Como funciona**
A análise demonstrou que o modelo **Logistic Regression** alcançou a melhor performance, com um **AUC de 0.8380** e uma **Sensibilidade (Recall) de 0.5051%** no conjunto de teste.

A simulação de previsão demonstrou a capacidade de classificação do modelo:
> **Caso de Alto Risco (Idade: 68, Glicose: 220, Doença Cardíaca: Sim)**
> Probabilidade de AVC: **89.60%**
> *Recomendação: ALTO RISCO! Intervenção clínica imediata é necessária.*

---

### 👥 **Equipe do Projeto**
<a href="https://github.com/amaro-netto" title="Amaro Netto"><img width="180" src="https://github.com/user-attachments/assets/b7a3a1bf-304a-4974-b75f-1d620ad6ecf1"/></a>

---

### ✅ **Conclusão e Insights**

1.  **Fatores Determinantes:** A análise de **Feature Importance** confirmou que a **Idade**, o **Nível de Glicose Médio** e a presença de **Doença Cardíaca** são os fatores de risco mais críticos para a previsão de AVC.
2.  **Capacidade Preditiva:** O modelo atingiu os objetivos de validação, provendo uma ferramenta valiosa para profissionais de saúde na tomada de decisões clínicas.
3.  **Recomendação:** Recomenda-se que a organização utilize este modelo para priorizar o acompanhamento e a intervenção preventiva em pacientes com esses fatores de risco elevados.
