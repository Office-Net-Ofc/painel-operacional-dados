# 📌 Ações Recomendadas (Baseadas em Dados)

Este documento define a lógica e os exemplos de ações recomendadas geradas a partir dos indicadores operacionais.

O objetivo é transformar dados em decisões práticas, reduzindo riscos e aumentando eficiência.

---

## 🎯 Objetivo
- Evitar falta de materiais críticos
- Reduzir capital parado em estoque
- Melhorar previsibilidade operacional
- Dar clareza de prioridade para execução

---

## 🧠 Regras para Geração de Ações

### 1️⃣ Ação: Reposição Imediata
**Condição:**
- status_estoque = CRÍTICO

**Mensagem recomendada:**
- "Reposição imediata: {produto} abaixo do mínimo ({quantidade_atual}/{estoque_minimo})."

**Prioridade:** Alta

---

### 2️⃣ Ação: Monitorar (Atenção)
**Condição:**
- status_estoque = ATENÇÃO

**Mensagem recomendada:**
- "Monitorar: {produto} próximo do mínimo ({quantidade_atual}/{estoque_minimo})."

**Prioridade:** Média

---

### 3️⃣ Ação: Reduzir Estoque Parado
**Condição:**
- dias_sem_movimentacao > 30

**Mensagem recomendada:**
- "Atenção a estoque parado: {produto} sem movimentação há {dias_sem_movimentacao} dias."

**Prioridade:** Média

---

### 4️⃣ Ação: Revisar Estoque Mínimo
**Condição:**
- produto entra em CRÍTICO com frequência (ex: recorrente em 30 dias)

**Mensagem recomendada:**
- "Revisar estoque mínimo: {produto} entra em crítico com frequência. Ajustar política de mínimo."

**Prioridade:** Média/Alta

---

## 📊 Saída Esperada (Formato)
As ações devem ser exibidas em lista com:
- Prioridade (Alta/Média/Baixa)
- Produto
- Motivo (crítico, atenção, parado)
- Sugestão (comprar, monitorar, revisar)

---

## ✅ Benefício Gerencial
Ao invés de analisar tabelas, o gestor recebe:
- o problema
- o motivo
- a prioridade
- a ação sugerida

Isso reduz tempo de decisão e aumenta consistência.
