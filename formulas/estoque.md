# 📦 Lógica de Estoque e Indicadores

Este documento descreve a lógica de tratamento e os principais indicadores (KPIs) utilizados para monitorar o estoque operacional.

---

## 🎯 Objetivo
Garantir visibilidade sobre:
- Nível de estoque
- Risco de falta de material
- Estoque parado
- Impacto financeiro

---

## 🧱 Estrutura de Dados (RAW_ESTOQUE)

Campos esperados:
- produto
- categoria
- quantidade_atual
- estoque_minimo
- custo_unitario
- data_ultima_movimentacao

---

## 🧮 Regras de Negócio

### 🔹 Status de Estoque
Classificação automática do nível de estoque:

- **CRÍTICO**  
  quantidade_atual ≤ estoque_minimo

- **ATENÇÃO**  
  quantidade_atual ≤ estoque_minimo × 1,5

- **OK**  
  quantidade_atual > estoque_minimo × 1,5

---

## 📊 KPIs Calculados

### 1️⃣ Itens em Estoque Crítico
Quantidade de produtos classificados como **CRÍTICO**.

**Objetivo:** Prevenir falta de material.

---

### 2️⃣ Percentual de Itens Críticos
Proporção de itens críticos em relação ao total do estoque.

**Objetivo:** Medir risco operacional.

---

### 3️⃣ Valor Total em Estoque
Soma de:

quantidade_atual × custo_unitario

**Objetivo:** Visibilidade financeira.

---

### 4️⃣ Estoque Parado
Itens sem movimentação acima de um período definido (ex: 30 dias).

**Objetivo:** Identificar capital imobilizado.

---

## ⚠️ Alertas Gerados
- Produtos abaixo do estoque mínimo
- Tendência de queda rápida no estoque
- Alto valor financeiro em itens parados

---

## 🔁 Uso no Dashboard
Os KPIs descritos neste documento alimentam:
- Cards de risco
- Gráficos de tendência
- Lista de ações recomendadas
