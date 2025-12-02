# Projeto — Análise Exploratória e Pré-Processamento de Dados  
### Dataset Olist E-Commerce  
### Disciplina: Ciência de Dados — UNIFSA

---

## 👥 Integrantes  
- **Guilherme Frazão**  
- **Eduardo Aguiar**

---

## 📦 Base de Dados Utilizada  
Dataset público do Olist disponibilizado no Kaggle:  
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

Tabelas utilizadas obrigatoriamente:
- `olist_orders_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_products_dataset.csv`

---

## 🎯 Objetivo do Projeto  
Aplicar o **Ciclo de Vida da Ciência de Dados** focado em:
- inspeção dos dados  
- limpeza  
- tratamento de inconsistências  
- análise exploratória (EDA)  
- feature engineering  
- padronização e normalização  
- preparação de um pipeline pré-processamento completo  

**Sem utilizar modelos de Machine Learning**, conforme orientação da disciplina.

---

## 🧹 Descrição do Processo de Tratamento dos Dados  

### ✔ 1. Limpeza Inicial  
- Remoção de duplicatas em todas as tabelas  
- Padronização de textos (lowercase, remoção de espaços extras)  
- Conversão correta de tipos (datas, números, strings)  

### ✔ 2. Tratamento de Valores Ausentes  
- Preenchimento de dimensões/peso por mediana  
- Datas ausentes mantidas (casos reais de não entrega)  
- Categorias desconhecidas preenchidas como `"missing"`

### ✔ 3. Detecção e Tratamento de Outliers  
- Método IQR  
- Aplicação de **capping (winsorization)**  
- Sem remoção de linhas  

### ✔ 4. Feature Engineering  
Criadas novas variáveis:
- `delivery_time_days`  
- `dias_atraso`  
- `n_items`  
- `valor_total_pedido`  

### ✔ 5. Preparação de Dados Categóricos  
- Agrupamento de categorias raras  
- One-Hot Encoding dentro do pipeline  

### ✔ 6. Normalização e Padronização  
Aplicado:  
- **StandardScaler**  
- **MinMaxScaler**  
Criados novos atributos com sufixos `_std` e `_mm`

### ✔ 7. Seleção de Atributos  
- Variance Threshold  
- Correlação  
- Análise semântica  

---

## 🚧 Principais Desafios Encontrados  
- Assimetria e grande quantidade de outliers  
- Mesclagem correta das tabelas (chaves order_id / product_id)  
- Tratamento de colunas de data com problemas  
- Diferenças grandes entre categorias de produtos  
- Construção de um pipeline reprodutível  

---

## 🧠 Principais Conclusões  
- Atrasos estão mais associados ao tempo total de entrega e categorias volumosas  
- Produtos pesados e grandes apresentaram fretes mais altos  
- Outliers influenciavam demais o comportamento das distribuições  
- A limpeza tornou os dados mais consistentes e interpretáveis  
- O pipeline final deixa os dados prontos para análises ou modelagem futura  

---

## 📁 Arquivos Importantes Neste Repositório  
- **Projeto_Olist_Analise_PreProcessamento.ipynb** — notebook completo  
- **olist_final_limpo.csv** — dataset limpo  
- **README.md** — documento atual  

---

## 📜 Licença  
Projeto acadêmico desenvolvido para a disciplina de Ciência de Dados — UNIFSA.

