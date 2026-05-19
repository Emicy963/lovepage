# LovePage — Presentes Digitais para Qualquer Ocasião Especial

Serviço de landing pages personalizadas para aniversários, surpresas, namoro, casamento e muito mais. Mercado principal: Angola (Luanda).

> **Domínio:** lovepage.art | **WhatsApp:** +244 928 301 450

## Conceito

O nome vem da intenção de **transmitir o teu amor** à pessoa desejada — não está limitado a casais. Qualquer pessoa que queira surpreender alguém especial com algo digital, personalizado e eterno.

## Quick Start

1. Abre `index.html` no navegador para ver a landing page de vendas
2. Os templates estão em `templates/[nome-do-tema]/index.html`
3. Para personalizar um template, usa Find/Replace com as variáveis abaixo

## Estrutura do Projeto

```
LovePage/
├── index.html                    # Landing page de vendas (dark theme)
├── README.md
├── docs/
│   ├── BUSINESS_MODEL.md         # Modelo de negócio e projeções
│   ├── PACKAGES_GUIDE.md         # Guia de produção por pacote
│   ├── BRANDING.md               # Identidade visual e tom de voz
│   ├── MARKETING_COPY.md         # Copies prontos para WhatsApp/redes
│   ├── PARTNERSHIP_PROPOSAL.md   # Proposta de parceria com floristas
│   ├── FLYERS_GUIDE.md           # Guia para os flyers
│   └── NOTION_GUIDE.md           # Gestão de encomendas no Notion
├── assets/
│   └── flyers/                   # Flyers PNG/PSD para marketing
└── templates/
    ├── birthday/                 # 🎂 NOVO - Aniversários (violeta/dourado)
    ├── classic-romance/          # ❤️  Básico - Vermelho/Dourado
    ├── modern-love/              # 💜  Básico - Rosa/Roxo gradientes
    ├── sunset-passion/           # 🌅  Básico - Laranja/Coral
    ├── ocean-breeze/             # 🌊  Básico - Azul/Verde-água
    ├── dark-elegance/            # 👑  Básico - Dark mode/Rose gold
    ├── premium/                  # 💝  PREMIUM - Cores custom + Timeline + Vídeo
    └── deluxe/                   # 🏆  DELUXE - Quiz + Design exclusivo + Ilimitado
```

## 🎨 Temas Disponíveis

| Tema                | Cores              | Estilo                 | Ideal para         |
| ------------------- | ------------------ | ---------------------- | ------------------ |
| **Classic Romance** | Vermelho + Dourado | Tradicional, romântico | Casais clássicos   |
| **Modern Love**     | Rosa + Roxo        | Moderno, gradientes    | Casais jovens      |
| **Sunset Passion**  | Laranja + Coral    | Caloroso, aconchegante | Casais apaixonados |
| **Ocean Breeze**    | Azul + Verde-água  | Sereno, calmo          | Casais tranquilos  |
| **Dark Elegance**   | Preto + Rose Gold  | Luxuoso, sofisticado   | Casais premium     |

## 🔧 Variáveis para Personalização

Abra o template desejado e use **Ctrl+H** (Find/Replace) para substituir:

### Informações Básicas

| Variável          | Descrição              | Exemplo                 |
| ----------------- | ---------------------- | ----------------------- |
| `{{NOME_ELE}}`    | Nome dele              | João                    |
| `{{NOME_ELA}}`    | Nome dela              | Maria                   |
| `{{DATA_INICIO}}` | Data que começaram     | 14 de Fevereiro de 2023 |
| `{{DIAS_JUNTOS}}` | Dias de relacionamento | 730                     |

### Mensagens

| Variável                 | Descrição                                          | Exemplo                 |
| ------------------------ | -------------------------------------------------- | ----------------------- |
| `{{MENSAGEM_PRINCIPAL}}` | Mensagem curta no início (1-2 frases)              |                         |
| `{{CARTA_AMOR}}`         | Carta de amor completa (pode ter múltiplas linhas) |                         |
| `{{DATA_CARTA}}`         | Data da carta                                      | 14 de Fevereiro de 2026 |

### Birthday (template `birthday/`)

| Variável                   | Descrição                            | Exemplo              |
| -------------------------- | ------------------------------------ | -------------------- |
| `{{NOME_ANIVERSARIANTE}}`  | Nome de quem faz anos                | Ana                  |
| `{{NOME_REMETENTE}}`       | Nome de quem oferece a surpresa      | Pedro                |
| `{{IDADE}}`                | Idade que faz                        | 25                   |
| `{{MENSAGEM_PRINCIPAL}}`   | Frase curta de abertura              |                      |
| `{{CARTA_PARABENS}}`       | Mensagem completa de aniversário     |                      |
| `{{DATA_CARTA}}`           | Data de criação da carta             | 19 de Maio de 2026   |

### Timeline

| Variável                | Descrição               | Exemplo                 |
| ----------------------- | ----------------------- | ----------------------- |
| `{{TIMELINE_DATA_1}}`   | Data do 1º momento      | Janeiro 2023            |
| `{{TIMELINE_TITULO_1}}` | Título do 1º momento    | Nosso Primeiro Encontro |
| `{{TIMELINE_DESC_1}}`   | Descrição do 1º momento | Foi num café...         |
| `{{TIMELINE_DATA_2}}`   | Data do 2º momento      |                         |
| `{{TIMELINE_TITULO_2}}` | Título do 2º momento    |                         |
| `{{TIMELINE_DESC_2}}`   | Descrição do 2º momento |                         |
| `{{TIMELINE_DATA_3}}`   | Data do 3º momento      |                         |
| `{{TIMELINE_TITULO_3}}` | Título do 3º momento    |                         |
| `{{TIMELINE_DESC_3}}`   | Descrição do 3º momento |                         |

### Fotos

As fotos usam URLs do Unsplash por padrão. Para substituir:

1. Encontre as tags `<img src="https://images.unsplash.com/..."`
2. Substitua pela URL da foto do cliente (Google Drive, Imgur, etc.)

**Dica:** Use imagens quadradas (1:1) para melhor resultado.

## 🎵 Música do Spotify

Para trocar a música:

1. Vá ao Spotify e encontre a música desejada
2. Clique em "Compartilhar" > "Copiar link do embed"
3. Substitua o código do iframe no template

```html
<iframe
    src="https://open.spotify.com/embed/track/CÓDIGO_DA_MÚSICA"
    ...
</iframe>
```

## 🚀 Deploy no Vercel

### Primeiro Deploy

1. Crie conta em [vercel.com](https://vercel.com)
2. Instale Vercel CLI: `npm i -g vercel`
3. No terminal, navegue até a pasta do projeto
4. Execute: `vercel`
5. Siga as instruções

### Deploy de Templates Individuais

Para cada cliente, você pode criar subdomínios:

```bash
# Entra na pasta do template personalizado
cd templates/classic-romance

# Faz deploy com nome específico
vercel --name joao-maria-lovepage
```

O cliente receberá um link como: `joao-maria-lovepage.vercel.app`

## 📋 Workflow de Produção

### Para cada cliente:

1. **Receber pedido** via WhatsApp
2. **Confirmar pagamento**
3. **Duplicar** a pasta do tema escolhido
4. **Personalizar** usando Find/Replace:
   - Nomes, datas, mensagens
   - Trocar fotos (via URL)
   - Trocar música do Spotify
5. **Testar** no navegador (mobile!)
6. **Deploy** no Vercel
7. **Enviar link** ao cliente

**Tempo médio:** 15-20 minutos por página básica

## 💰 Preços Sugeridos

| Pacote      | Preço      | Inclui                                              |
| ----------- | ---------- | --------------------------------------------------- |
| **Básico**  | 5.000 AOA  | Template + 10 fotos + música                        |
| **Premium** | 12.000 AOA | Básico + cores custom + 30 fotos + vídeo + timeline |
| **Deluxe**  | 25.000 AOA | Premium + design exclusivo + fotos ilimitadas       |

## 📱 Landing Page de Vendas

O arquivo `index.html` na raiz é a landing page de vendas.

**Para configurar:**

1. O número de WhatsApp já está configurado para `+244 928 301 450` — altere em `index.html` se necessário (pesquisa por `wa.me/244928301450`)
2. Atualize os depoimentos com feedback real de clientes
3. Ajuste os preços se necessário

## ✅ Checklist Pré-Entrega

Antes de enviar para o cliente:

- [ ] Nomes estão corretos
- [ ] Todas as fotos carregam
- [ ] Música do Spotify toca
- [ ] Página responsiva (testar no celular)
- [ ] Links funcionam
- [ ] Sem erros de português
- [ ] Timeline faz sentido cronológico

## 🆘 Problemas Comuns

**Fotos não carregam:**

- Verifique se a URL da imagem é pública
- Use serviços como Imgur ou Google Photos com link público

**Música não toca:**

- Verifique se o link do Spotify está correto
- Algumas músicas têm restrições regionais

**Página lenta:**

- Otimize tamanho das imagens (máx. 500KB cada)
- Use formato WebP se possível

## 📞 Suporte

Dúvidas sobre o uso? Consulte este README ou entre em contato.

---

**Feito com 💕 para surpreender quem amas — em qualquer ocasião.**
