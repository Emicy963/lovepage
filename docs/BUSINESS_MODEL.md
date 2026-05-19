# LovePage Angola — Modelo de Negócio

## Visão Geral

**Produto:** Landing pages personalizadas para qualquer ocasião especial  
**Mercado:** Angola (foco Luanda) — qualquer pessoa que queira surpreender alguém  
**Modelo:** Serviço de produção unitária com 3 tiers de preço  
**Posicionamento:** Evergreen — aniversários (12 meses/ano), namoro, casamento, surpresas  
**Domínio:** lovepage.art

### Ocasiões-alvo (por prioridade de volume)

1. **Aniversários** — evergreen, acontecem todos os meses, template dedicado
2. **Surpresas especiais** — declarações, pedidos de desculpas, homenagens
3. **Namoro / Casamento** — alta emoção, maior ticket médio
4. **Família** — Dia das Mães, Pais, homenagens especiais (sazonais)

---

## Estrutura de Preços

| Pacote      | Preço      | Margem | Tempo Produção | Lucro/h       |
| ----------- | ---------- | ------ | -------------- | ------------- |
| **Básico**  | 5.000 AOA  | ~95%   | 15-20 min      | ~15.000 AOA/h |
| **Premium** | 12.000 AOA | ~90%   | 30-45 min      | ~16.000 AOA/h |
| **Deluxe**  | 25.000 AOA | ~85%   | 60-90 min      | ~16.000 AOA/h |

### Custos Fixos

- Domínio: 0 AOA (usando subdomínios Vercel gratuitos)
- Hosting: 0 AOA (Vercel free tier)
- Marketing: 0 AOA na fase de validação (boca-a-boca e WhatsApp Status)

### Custos Variáveis

- Apenas tempo do produtor

---

## Funil de Vendas (Processo Correto)

O produto é emocional e visual. A venda acontece com demo ao vivo, não com descrição verbal.

```text
Lead qualificado (alguém com ocasião real nos próximos 30 dias)
        ↓
Demo parcial gratuita com fotos reais do cliente (20 minutos)
        ↓
Cliente vê o próprio conteúdo na página → impacto emocional
        ↓
"Queres a versão completa?" → confirmação de pacote
        ↓
Pagamento 100% antecipado → produção → entrega → pedido de referral
```

### Regra principal de conversão

Nunca pedir pagamento sem a pessoa ter visto a própria demo com as próprias fotos.

---

## Projeções de Receita

### Meta fase de validação: 5 vendas convertidas

| Mix de Vendas | Qtd   | Receita        |
| ------------- | ----- | -------------- |
| Básico (60%)  | 3     | 15.000 AOA     |
| Premium (30%) | 1     | 12.000 AOA     |
| Deluxe (10%)  | 1     | 25.000 AOA     |
| **TOTAL**     | **5** | **52.000 AOA** |

**Tempo total de produção:** ~4 horas

### Meta mês 1 (após validação confirmada)

| Mix de Vendas | Qtd    | Receita         |
| ------------- | ------ | --------------- |
| Básico (50%)  | 10     | 50.000 AOA      |
| Premium (35%) | 5      | 60.000 AOA      |
| Deluxe (15%)  | 2      | 50.000 AOA      |
| **TOTAL**     | **17** | **160.000 AOA** |

---

## Canais de Aquisição (por ROI)

| Canal                    | Custo | Conversão | Prioridade  |
| ------------------------ | ----- | --------- | ----------- |
| Referral de cliente      | 0     | Muito alta | **#1**      |
| Demo parcial grátis      | tempo | Alta       | **#2**      |
| WhatsApp Status          | 0     | Média      | **#3**      |
| Parceria floristas       | 0–10% | Alta       | **#4**      |
| Grupos WhatsApp          | 0     | Baixa      | #5          |
| Instagram/TikTok         | tempo | Baixa-Média | #6 (futuro)|
| Anúncios pagos           | dinheiro | Variável | #7 (futuro)|

---

## Fluxo Operacional

### 1. Qualificação do lead

```text
Contacto recebido ou referral
    ↓
Verificar: há uma ocasião real nos próximos 30 dias?
    ↓
Não → arquivar, manter contacto para futura ocasião
Sim → avançar para demo
```

### 2. Demo parcial (pré-venda)

```text
Pedir 2-3 fotos + texto curto (máximo)
    ↓
Montar rascunho no template base (20 min)
    ↓
Deploy em URL Vercel temporário
    ↓
Enviar link sem mencionar preço ainda
    ↓
Aguardar reação (o produto fecha a venda)
    ↓
"Queres a versão completa com todas as funcionalidades?"
```

### 3. Venda

```text
Confirmação do pacote
    ↓
Enviar dados de pagamento (Multicaixa Express / Transferência)
    ↓
Confirmar comprovativo
    ↓
Recolher assets completos (fotos, textos, música Spotify)
```

### 4. Produção

```text
Escolher template base
    ↓
Find/Replace variáveis (Ctrl+H no VSCode)
    ↓
Adicionar fotos
    ↓
Configurar música Spotify
    ↓
Testar no mobile (obrigatório)
    ↓
Deploy Vercel com URL definitivo
    ↓
Enviar link ao cliente
```

### 5. Pós-venda

```text
Confirmar satisfação (24h após entrega)
    ↓
Pedir depoimento (áudio ou texto curto)
    ↓
Pedir referral: "Conheces alguém com aniversário em breve?"
    ↓
Oferecer upsell para próxima ocasião (se aplicável)
```

---

## Canais de Parceria

### Floristas (maior ROI)

Proposta: por cada cliente referenciado que feche venda, a florista recebe 10% do valor.

- Básico 5.000 → florista ganha 500 AOA por referral
- Premium 12.000 → florista ganha 1.200 AOA por referral
- Deluxe 25.000 → florista ganha 2.500 AOA por referral

Abordagem: presencial, não WhatsApp. Ver `docs/PARTNERSHIP_PROPOSAL.md` para o script completo.

### Outros parceiros potenciais

- Lojas de presentes
- Fotógrafos de casal (referral mútuo)
- Salões de beleza (clientes que se preparam para surpresas)

---

## Gestão de Capacidade

| Pacote  | Tempo  | Máximo/dia (4h produção) |
| ------- | ------ | ------------------------ |
| Básico  | 20 min | 12                       |
| Premium | 45 min | 5                        |
| Deluxe  | 90 min | 2                        |

Limite prático: 3-4 pedidos/dia em modo solo. Acima disso, priorizar Premium e Deluxe por lucro/hora.

---

## Políticas

### Pagamento

- 100% antecipado (obrigatório, sem exceções)
- Métodos: Multicaixa Express, Transferência bancária

### Assets do cliente

- Cliente deve enviar fotos e textos em 24h após pagamento
- Atrasos do cliente não alteram o prazo de entrega prometido — prazo conta a partir do recebimento dos assets

### Revisões

- 2 revisões incluídas no preço
- Revisão adicional: 1.000 AOA cada

### Reembolso

- Antes de iniciar produção: 100%
- Após iniciar produção: 0%

---

## Milestones de Validação

| Milestone        | Critério                                         | Ação seguinte                         |
| ---------------- | ------------------------------------------------ | ------------------------------------- |
| Validação básica | 3 demos feitas, pelo menos 2 convertidas         | Continuar processo, pedir referrals   |
| Validação real   | 5 vendas pagas entregues, 3 depoimentos          | Activar WhatsApp Status regularmente  |
| Escala inicial   | 10 vendas, 1 parceria florista activa            | Considerar Instagram/redes sociais    |
| Escala média     | 25 vendas, 2-3 parcerias activas, 10 depoimentos | Avaliar automação ou segundo operador |

Não avançar para o milestones seguinte sem completar o anterior.
