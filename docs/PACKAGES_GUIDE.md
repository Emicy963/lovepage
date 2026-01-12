# 📦 Guia de Pacotes: Básico vs Premium vs Deluxe

## Resumo das Diferenças

| Feature          | Básico (5k) | Premium (12k) | Deluxe (25k)    |
| ---------------- | ----------- | ------------- | --------------- |
| Template base    | ✅          | ✅            | ❌ Design único |
| Fotos            | 10          | 30 + 1 vídeo  | Ilimitadas      |
| Timeline         | ❌          | ✅ 3 momentos | ✅ 5+ momentos  |
| Cores custom     | ❌          | ✅            | ✅              |
| Animações extras | ❌          | ✅            | ✅ Premium      |
| Quiz do casal    | ❌          | ❌            | ✅              |
| QR Code físico   | ❌          | ❌            | ✅              |
| Tempo produção   | 15-20 min   | 30-45 min     | 60-90 min       |
| Prazo entrega    | 24h         | 48h           | 72h             |

---

## 📦 PACOTE BÁSICO (5.000 AOA)

### O que está incluso

- 1 tema à escolha (dos 5 disponíveis)
- Até 10 fotos
- Hero com foto principal
- Galeria de fotos
- 1 música do Spotify
- Seção de carta de amor
- Design responsivo

### O que NÃO está incluso

- Timeline do relacionamento
- Cores personalizadas (usa cores do tema)
- Vídeos
- Animações especiais

### Como produzir (15-20 min)

1. **Duplicar template** (1 min)

   ```
   Copia pasta do tema escolhido
   Renomeia: cliente-nome
   ```

2. **Find/Replace variáveis** (5 min)

   - Ctrl+H no VSCode
   - Substitui todas as `{{VARIÁVEIS}}`

3. **Adicionar fotos** (5 min)

   - Recebe fotos do cliente (WhatsApp/Drive)
   - Faz upload para serviço (Imgur/Cloudinary)
   - Substitui URLs das imagens

4. **Música Spotify** (2 min)

   - Pede link da música ao cliente
   - Pega embed code
   - Substitui iframe

5. **Deploy** (2 min)

   ```bash
   cd pasta-cliente
   vercel --name cliente-lovepage
   ```

6. **Teste rápido** (2 min)
   - Abre no celular
   - Verifica fotos, nomes, música

---

## 📦 PACOTE PREMIUM (12.000 AOA)

### O que está incluso

Tudo do Básico +:

- Até 30 fotos + 1 vídeo
- Timeline do relacionamento (3 momentos)
- Cores personalizadas
- Animações melhoradas
- Suporte WhatsApp prioritário

### Como produzir (30-45 min)

#### 1-5. Mesmo processo do Básico (15 min)

#### 6. Timeline personalizada (10 min)

```
Preencher:
{{TIMELINE_DATA_1}} = "Janeiro 2023"
{{TIMELINE_TITULO_1}} = "Primeiro Encontro"
{{TIMELINE_DESC_1}} = "Nos conhecemos no café..."

{{TIMELINE_DATA_2}} = "Março 2023"
{{TIMELINE_TITULO_2}} = "Primeiro Beijo"
{{TIMELINE_DESC_2}} = "Depois do cinema..."

{{TIMELINE_DATA_3}} = "Dezembro 2023"
{{TIMELINE_TITULO_3}} = "Viagem Juntos"
{{TIMELINE_DESC_3}} = "Primeira viagem a dois..."
```

#### 7. Cores personalizadas (5 min)

No `<script>` do Tailwind config:

```javascript
tailwind.config = {
  theme: {
    extend: {
      colors: {
        romance: {
          primary: "#COR_ESCOLHIDA", // Cor principal
          secondary: "#COR_SECUNDÁRIA", // Cor de destaque
          light: "#COR_FUNDO", // Background
          dark: "#COR_TEXTO", // Texto
        },
      },
    },
  },
};
```

**Dica:** Pergunte ao cliente cor favorita e use:

- [Coolors.co](https://coolors.co) para gerar paleta
- [ColorHunt](https://colorhunt.co) para inspiração

#### 8. Adicionar vídeo (5 min)

```html
<!-- Substituir uma foto por vídeo -->
<video controls class="w-full rounded-xl">
  <source src="URL_DO_VIDEO" type="video/mp4" />
</video>
```

Opções de hosting para vídeo:

- YouTube (embed privado)
- Google Drive (link público)
- Cloudinary (upload direto)

#### 9. Deploy + Teste (5 min)

---

## 📦 PACOTE DELUXE (25.000 AOA)

### O que está incluso

Tudo do Premium +:

- Design 100% exclusivo
- Fotos e vídeos ilimitados
- Timeline expandida (5+ momentos)
- Quiz interativo sobre o casal
- QR Code em cartão físico
- Animações premium

### Como produzir (60-90 min)

#### 1-8. Mesmos passos do Premium (45 min)

#### 9. Quiz do Casal (15 min)

Adicionar seção de quiz interativo:

```html
<!-- Quiz Section -->
<section class="py-20 px-4 bg-white">
  <div class="max-w-3xl mx-auto text-center">
    <h2 class="text-3xl font-bold mb-8">💕 Você conhece nosso amor?</h2>

    <div id="quiz" class="space-y-6">
      <!-- Pergunta 1 -->
      <div class="quiz-question bg-gray-50 rounded-xl p-6" data-correct="a">
        <p class="font-semibold mb-4">Onde foi nosso primeiro encontro?</p>
        <div class="grid grid-cols-2 gap-3">
          <button
            onclick="checkAnswer(this, 'a')"
            class="quiz-btn p-3 rounded-lg border-2 hover:bg-pink-100"
          >
            Café Central
          </button>
          <button
            onclick="checkAnswer(this, 'b')"
            class="quiz-btn p-3 rounded-lg border-2 hover:bg-pink-100"
          >
            Shopping
          </button>
          <button
            onclick="checkAnswer(this, 'c')"
            class="quiz-btn p-3 rounded-lg border-2 hover:bg-pink-100"
          >
            Praia
          </button>
          <button
            onclick="checkAnswer(this, 'd')"
            class="quiz-btn p-3 rounded-lg border-2 hover:bg-pink-100"
          >
            Faculdade
          </button>
        </div>
      </div>

      <!-- Adicionar mais perguntas... -->
    </div>

    <div
      id="quiz-result"
      class="hidden mt-8 p-6 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 text-white"
    >
      <p class="text-2xl font-bold">
        🎉 Você acertou <span id="score">0</span>/5!
      </p>
    </div>
  </div>
</section>

<script>
  let score = 0;
  let answered = 0;
  const total = 5;

  function checkAnswer(btn, answer) {
    const question = btn.closest(".quiz-question");
    const correct = question.dataset.correct;

    question.querySelectorAll(".quiz-btn").forEach((b) => (b.disabled = true));

    if (answer === correct) {
      btn.classList.add("bg-green-500", "text-white");
      score++;
    } else {
      btn.classList.add("bg-red-500", "text-white");
      question
        .querySelector(`[onclick*="'${correct}'"]`)
        .classList.add("bg-green-500", "text-white");
    }

    answered++;
    if (answered === total) {
      document.getElementById("score").textContent = score;
      document.getElementById("quiz-result").classList.remove("hidden");
    }
  }
</script>
```

**Perguntas sugeridas para o quiz:**

1. Onde foi o primeiro encontro?
2. Qual a música favorita do casal?
3. Qual a comida favorita dele/dela?
4. Qual foi a primeira viagem juntos?
5. Qual o apelido carinhoso?

#### 10. QR Code Físico (10 min)

1. **Gerar QR Code:**

   - Acessa [qr-code-generator.com](https://www.qr-code-generator.com)
   - Cola URL da página
   - Baixa PNG em alta resolução

2. **Criar cartão para impressão:**

   - Template no Canva (grátis)
   - Tamanho: cartão de visita (8.5 x 5.5 cm)
   - Frente: QR Code + "Escaneie para ver nossa história"
   - Verso: Nomes + Data especial

3. **Opção de entrega:**
   - Envia PDF para cliente imprimir
   - OU imprime e entrega (custo extra opcional)

#### 11. Timeline Expandida (5 min)

Adicionar mais itens na timeline (5-7 momentos especiais)

#### 12. Animações Premium (5 min)

Adicionar efeitos extras:

- Parallax no hero
- Confetti na carta de amor
- Transições mais elaboradas

#### 13. Deploy + Teste completo (5 min)

---

## 💡 Upsell: Básico → Premium

### Script WhatsApp

```
Oi [nome]! Vi que você escolheu o pacote Básico.

Só pra você saber: o Premium por +7.000 AOA inclui:
✅ Timeline contando a história de vocês
✅ Cores personalizadas (a favorita dela/dele!)
✅ Até 30 fotos + 1 vídeo
✅ Animações mais bonitas

A maioria dos clientes escolhe o Premium porque a Timeline emociona MUITO.

Quer fazer upgrade? Ainda dá tempo! 😊
```

**Taxa de conversão esperada:** 20-30%

---

## 💡 Upsell: Premium → Deluxe

### Script WhatsApp

```
[nome], seu Premium ficou LINDO! 🔥

Pensei em você: que tal adicionar um Quiz do Casal?

É uma seção interativa onde quem abrir a página responde perguntas sobre vocês. Super divertido!

Upgrade pro Deluxe: só +13.000 AOA
- Quiz personalizado
- QR Code em cartão físico pra presente
- Design ainda mais exclusivo

Topa? Consigo entregar junto! 💕
```

---

## ⚠️ Limites Importantes

| Regra                   | Motivo                  |
| ----------------------- | ----------------------- |
| Máx 5 Deluxe total      | Muito tempo de produção |
| Máx 2 Deluxe/dia        | Qualidade > Quantidade  |
| Deadline Deluxe: 10/Fev | Precisa de 72h + buffer |
| Pré-pagamento 100%      | Evita cancelamentos     |
| 2 revisões max          | Protege seu tempo       |
