# LovePage — Guia de Hospedagem e Domínio Personalizado

Referência passo a passo para fazer deploy de uma página de cliente e configurar
o subdomínio `nome.lovepage.art`. Usa este guia sempre que criares uma nova página.

---

## Pré-requisitos

- Conta GitHub: `github.com/Emicy963`
- Conta Vercel ligada ao GitHub acima (conta separada para clientes)
- Domínio `lovepage.art` gerido no Cloudflare
- Pasta do cliente criada localmente em `clients/nome-cliente/`

---

## Parte 1 — Preparar a Pasta do Cliente

Estrutura obrigatória antes de fazer qualquer deploy:

```text
clients/
  nome-cliente/
    index.html        ← página personalizada
    assets/
      foto1.jpeg
      foto2.jpeg
      foto3.jpeg
```

Confirmar antes de avançar:

- [ ] `index.html` tem o nome correcto do cliente
- [ ] Caminhos das fotos em `index.html` correspondem exactamente aos ficheiros em `assets/`
- [ ] Página testada localmente (abrir `index.html` no browser)
- [ ] Testada no telemóvel (usar DevTools → Toggle Device Toolbar)

---

## Parte 2 — Commit e Push para GitHub

```text
git add clients/nome-cliente/
git commit -m "feat(clients): add nome-cliente birthday/occasion demo page"
git push origin develop
```

Se for uma entrega final (não demo), faz merge para main depois:

```text
git checkout main
git merge --no-ff develop -m "merge: develop -> main (nome-cliente page)"
git push origin main
git checkout develop
```

---

## Parte 3 — Criar Projecto no Vercel

1. Vai a **vercel.com** → **Add New… → Project**
2. Clica **Import Git Repository**
3. Selecciona o repo **`Emicy963/lovepage`**
4. Antes de confirmar, expande **"Build and Output Settings"**
5. No campo **Root Directory**, escreve exactamente: `clients/nome-cliente`

   > ⚠️ Este passo é crítico. Sem isto o Vercel serve o site inteiro.

6. Clica **Deploy**
7. Aguarda ~30 segundos → o Vercel gera um URL temporário tipo:
   `lovepage-nome-cliente.vercel.app`

8. Abre esse URL no telemóvel e confirma que:
   - [ ] As fotos carregam (não aparecem imagens quebradas)
   - [ ] O nome do cliente está correcto
   - [ ] A música do Spotify aparece
   - [ ] O scroll reveal funciona (secções aparecem ao descer)

---

## Parte 4 — Subdomínio Personalizado (Premium e Deluxe)

> Para o Básico, o URL temporário do Vercel já é suficiente.
> Subdomínio só para Premium e Deluxe.

### 4.1 — Adicionar domínio no Vercel

No dashboard do projecto recém-criado:

```text
Settings → Domains → Add
```

Escreve: `nome-cliente.lovepage.art` → clica **Add**

O Vercel mostra uma tabela com o registo a criar:

| Type  | Name         | Value                              | Proxy    |
|-------|--------------|------------------------------------|----------|
| CNAME | nome-cliente | `xxxxxxxx.vercel-dns-017.com`      | Disabled |

> O valor CNAME é único para cada projecto — copia-o exactamente como aparece.
> O ponto final no final (`.com.`) é notação DNS — não o incluas no Cloudflare.

### 4.2 — Adicionar registo no Cloudflare

1. Vai a **dash.cloudflare.com** → zona **`lovepage.art`**
2. Clica em **DNS → Records → Add record**
3. Preenche:

   | Campo         | Valor                                        |
   |---------------|----------------------------------------------|
   | Type          | `CNAME`                                      |
   | Name          | `nome-cliente` (só o prefixo, sem o domínio) |
   | Target        | valor copiado do Vercel (sem o ponto final)  |
   | Proxy status  | **DNS only** (nuvem cinzenta ⚫)             |
   | TTL           | Auto                                         |

   > ⚠️ O Proxy tem de estar **desactivado** (cinzento).
   > Se ficar laranja (Proxied), o Vercel não consegue verificar o domínio.

4. Clica **Save**

### 4.3 — Verificar no Vercel

Volta ao Vercel → **Settings → Domains** → clica **Refresh** ao lado do domínio.

- `Invalid Configuration` → aguarda 2-10 minutos e volta a clicar Refresh
- `Valid Configuration ✅` → domínio activo, pronto a partilhar

---

## Parte 5 — Entrega ao Cliente

Após o domínio estar activo (`✅` no Vercel):

1. Testa o URL final no telemóvel
2. Envia ao cliente com a mensagem de entrega
3. Regista no controlo de clientes (nome, URL, data de entrega, data de expiração)

---

## Controlo de Clientes (Tabela de Referência)

Mantém esta tabela actualizada. A data de expiração é sempre **1 ano após a entrega**.

| Cliente       | Pacote  | URL                          | Entrega    | Expiração  |
|---------------|---------|------------------------------|------------|------------|
| Bércia O.     | Básico  | lovepage-bercia.vercel.app   | 2026-05-20 | 2027-05-20 |
| Sâmia M.      | Básico  | (a definir)                  | —          | —          |

> Adiciona uma linha por cada cliente entregue.
> Usa `YYYY-MM-DD` para facilitar ordenação.

---

## Resolução de Problemas Comuns

### Fotos não carregam

- Confirma que os nomes dos ficheiros em `assets/` coincidem exactamente com os `src=""` no HTML
- Nomes são case-sensitive: `Samia1.jpeg` ≠ `samia1.jpeg`
- Confirma que o push incluiu os ficheiros de imagem (verificar no GitHub)

### Domínio continua "Invalid Configuration" após 15 min

- Confirma que o registo CNAME está no Cloudflare com Proxy **desactivado**
- Confirma que o Name é apenas o prefixo (`nome-cliente`) e não o domínio completo
- Confirma que o valor Target não tem o ponto final (`.`)
- Tenta limpar a cache do DNS: `ipconfig /flushdns` (Windows) ou aguarda propagação

### Root Directory errado — Vercel serve o site principal

- Vai ao projecto no Vercel → **Settings → General → Root Directory**
- Edita para `clients/nome-cliente`
- Faz **Redeploy** (sem necessidade de novo push)

### O projeto não aparece no Vercel ao importar

- Confirma que fizeste push para o branch correcto antes de criar o projecto
- O Vercel lê o estado actual do repo no momento do import

---

## Renovação Anual

1 mês antes da data de expiração, envia ao cliente:

```md
Ei [nome]! A página da [aniversariante] renova daqui a 1 mês.

Para manter online mais 1 ano: 1.500 AOA.

Queres renovar? 😊
```

Para renovar: o projecto Vercel mantém-se activo automaticamente enquanto
a conta não atingir os limites. A "renovação" é um acordo comercial —
não há acção técnica necessária da tua parte além de confirmar o pagamento.

Se o cliente **não renovar**: remove o projecto do Vercel para libertar espaço.
A pasta `clients/nome-cliente/` no GitHub mantém-se como arquivo.
