# 📒 Guia: Template Notion para Controle Financeiro

## Estrutura Recomendada

Cria um **Database** no Notion com as seguintes propriedades:

---

## 🗂️ Propriedades do Database "Pedidos LovePage"

| Propriedade        | Tipo     | Opções/Formato                                                         |
| ------------------ | -------- | ---------------------------------------------------------------------- |
| **Cliente**        | Title    | Nome do cliente                                                        |
| **WhatsApp**       | Phone    | Número com +244                                                        |
| **Pacote**         | Select   | Básico, Premium, Deluxe                                                |
| **Valor**          | Number   | AOA (formato moeda)                                                    |
| **Status**         | Select   | 🟡 Aguardando pgto, 🟢 Pago, 🔵 Em produção, ✅ Entregue, ❌ Cancelado |
| **Data Pedido**    | Date     | dd/mm/aaaa                                                             |
| **Data Pagamento** | Date     | dd/mm/aaaa                                                             |
| **Data Entrega**   | Date     | dd/mm/aaaa                                                             |
| **Tema Escolhido** | Select   | Classic, Modern, Sunset, Ocean, Dark                                   |
| **Link Entregue**  | URL      | Link do Vercel                                                         |
| **Depoimento**     | Checkbox | ✓ se cliente deu depoimento                                            |
| **Notas**          | Text     | Observações                                                            |

---

## 📊 Views Úteis

### 1. Kanban por Status

Agrupa por "Status" para ver pipeline visual:

```
🟡 Aguardando → 🟢 Pago → 🔵 Produção → ✅ Entregue
```

### 2. Tabela Financeira

Filtra: Status = "Pago" ou "Entregue"
Soma: Valor (no rodapé)

### 3. Calendário de Entregas

View Calendar por "Data Entrega"

### 4. Lista de Produção do Dia

Filtra: Status = "Em produção"
Ordena: Data Entrega (crescente)

---

## 🧮 Fórmulas Úteis

### Dias até entrega

```
dateBetween(prop("Data Entrega"), now(), "days")
```

### Lucro estimado (90% margem)

```
prop("Valor") * 0.9
```

### Status emoji automático

```
if(prop("Status") == "Aguardando pgto", "🟡",
if(prop("Status") == "Pago", "🟢",
if(prop("Status") == "Em produção", "🔵",
if(prop("Status") == "Entregue", "✅", "❌"))))
```

---

## 📈 Dashboard de Resumo

Cria uma página separada "Dashboard" com:

### Blocos de Métricas (Linked Database)

1. **Total Arrecadado**

   - Filter: Status = Pago OR Entregue
   - Sum: Valor

2. **Pedidos Pendentes**

   - Filter: Status = Aguardando OR Em produção
   - Count: All

3. **Taxa de Conversão**
   - (Pagos / Total) \* 100

### Gráficos

- Vendas por Pacote (Pie chart)
- Vendas por Dia (Timeline)
- Status Pipeline (Bar chart)

---

## 🚀 Como Criar

### Passo a Passo

1. **Novo Database**

   - Página nova → `/database` → "Table - Full page"
   - Nomeia: "Pedidos LovePage"

2. **Adicionar Propriedades**

   - Clica no "+" no header
   - Adiciona cada propriedade da lista acima

3. **Criar Views**

   - Clica em "+ Add a view"
   - Cria: Board (kanban), Calendar, Table

4. **Modelo de Pedido**
   - Abre um item
   - Clica "..." → "Templates" → "New template"
   - Cria template com campos pré-preenchidos

---

## 📱 Template de Entrada Rápida

Quando receber pedido, preenche:

```
Cliente: [Nome]
WhatsApp: +244 XXX XXX XXX
Pacote: [Básico/Premium/Deluxe]
Valor: [5000/12000/25000]
Status: 🟡 Aguardando pgto
Data Pedido: [hoje]
Tema: [escolhido]
```

Após pagamento:

```
Status: 🟢 Pago
Data Pagamento: [hoje]
Data Entrega: [+24h/48h/72h]
```

Após entrega:

```
Status: ✅ Entregue
Link Entregue: [URL]
```

---

## 💡 Dicas

1. **Mobile:** Usa o app Notion no celular para updates rápidos
2. **WhatsApp:** Copia link do Notion e salva nos contatos
3. **Backup:** Exporta para CSV semanalmente
4. **Relatório:** No final, exporta tudo para análise

---

## 🔗 Alternativas ao Notion

Se preferir algo mais simples:

| Ferramenta        | Prós               | Contras           |
| ----------------- | ------------------ | ----------------- |
| **Google Sheets** | Familiar, fórmulas | Menos visual      |
| **Trello**        | Kanban simples     | Sem cálculos      |
| **Airtable**      | Poderoso           | Curva aprendizado |
| **Excel**         | Offline            | Não colaborativo  |

Para começar rápido: **Google Sheets** é suficiente!
