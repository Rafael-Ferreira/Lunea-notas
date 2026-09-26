# 🌐 Lunea — Análise do site (26/09/2026)

> Análise feita pela **Luna** direto da web (sem acesso ao servidor).
> Contexto: Rafael está criando um **site novo** (Manus / Lovable) e vai **aposentar o WordPress**.

---

## 🔴 Estado atual: o site está FORA DO AR

| | |
|---|---|
| **Status** | **HTTP 500** em todas as páginas |
| **Mensagem** | *"Erro › WordPress — Há um erro crítico no seu site"* |
| **Natureza** | Erro **fatal do PHP** |
| **Tempo de resposta** | **0,15s** (instantâneo e consistente em 3 tentativas) |

**Páginas testadas (todas 500):**
```
https://lunea.com.br/          → 500
https://lunea.com.br/contato   → 500
https://lunea.com.br/sobre     → 500
https://lunea.com.br/wp-login  → 500
```

➡️ **Leitura:** como os arquivos estáticos respondem normal e só o PHP quebra, o
problema é **código do WordPress** (plugin / tema / core) — não é hospedagem,
não é sobrecarga, não é DNS.

**Como não vamos mais usar WordPress, isso não precisa ser consertado** — é
apenas o registro do estado.

---

## ✅ O que está saudável

| Item | Situação |
|---|---|
| **Domínio** | ✅ de Rafael Ferreira, expira **09/04/2027** |
| **DNS** | ✅ resolve (A: `88.222.222.12`, `84.32.84.82`) |
| **Nameservers** | `ns1/ns2.dns-parking.com` (Hostinger) |
| **Certificado SSL** | ✅ válido (Let's Encrypt, até **01/11/2026**) |
| **Servidor web** | ✅ responde |
| **Arquivos estáticos** | ✅ 200 (`wp-includes`, `wp-content`, `readme.html`) |
| **Subdomínio `suporte.lunea.com.br`** | ✅ **funcionando** (WordPress 6.8.10 + Elementor 4.1.4) |

---

## 📧 E-mail (importante!)

```
MX:  mx1.hostinger.com / mx2.hostinger.com
SPF: _spf.mail.hostinger.com
TXT: brevo-code:f3754f382d4c6195c23d96b4eb556b49   ← Brevo (marketing)
```

✅ **Sem risco nesta migração** — como a **hospedagem NÃO será cancelada**, o
e-mail `@lunea.com.br` continua funcionando normalmente.

> ⚠️ **Regra:** ao mexer no DNS para apontar o site novo, **NÃO tocar nos
> registros MX, SPF nem no TXT do Brevo.**

---

## 🏠 Hospedagem

| Item | Valor |
|---|---|
| Conta | `u529990366` |
| Diretório do site | `/home/u529990366/domains/lunea.com.br/public_html` |
| Tipo | WordPress (addon) |
| Criado em | 17/12/2023 |
| Co-pagador | `client_id 38382557`, `order_id 200787858` |

---

## 🎯 Plano do Rafael (confirmado)

- ❌ **Não** vai cancelar a hospedagem (o e-mail fica)
- 🚫 Vai **aposentar o WordPress**
- 🆕 Está criando o site novo com **Manus** ou **Lovable**
- 📋 Objetivo atual: só um **relatório** do estado, sem consertar nada

### Os dois caminhos para o site novo (ambos preservam o e-mail)

**A) Hospedar na própria Hostinger** *(mais simples)*
Substituir o conteúdo de `public_html` pelo build estático do site novo.
- ✅ zero mudança de DNS · ✅ e-mail intacto · ✅ um só lugar

**B) Hospedar onde o Lovable/Manus publicar** (Vercel, Netlify…)
Apontar um registro **A** ou **CNAME** para lá.
- ✅ e-mail intacto (**desde que não mexer nos MX**)
- ⚠️ a hospedagem Hostinger passa a existir só pelo e-mail (custo a revisar)

---

## 📦 Inventário de conteúdo — PENDENTE

Ainda **não** foi feito: preciso de **acesso SSH** para listar os textos e as
imagens que valham a pena reaproveitar no site novo.

### Para destravar
1. **hPanel** → **Avançado** → **Acesso SSH** → **Chaves SSH** → adicionar:
   ```
   ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIL+gJdI8aMr0TONL1JrAVhXac9dF0b8aHX7f721TK3Vh luna-hermes@guardion
   ```
2. Informar **host**, **porta** e **usuário** para a Luna

### O que a Luna vai trazer depois disso
- Quantas páginas / posts existem e **os textos** (para reaproveitar)
- Quantas imagens e quanto pesam (o acervo visual)
- Tema e plugins usados (o que o site fazia: formulário? SEO? loja?)
- O erro exato do 500 (só para registro)
- Lista do que vale levar para o site novo

---

## 💡 Recomendações para o site novo

- Use **staging** para testar antes de subir — um erro como esse nunca derruba
  a produção
- Desative **atualizações automáticas** de plugins (causa nº 1 desse tipo de queda)
- Compare com o `suporte.lunea.com.br` (que está funcionando) para descobrir
  diferenças de versão quando algo quebrar
- Como o site novo será estático (React do Lovable), ele **não sofre** com esse
  tipo de erro de PHP

---

*Análise feita por fora (sem acesso ao servidor). Ver também [[README]] do cofre.*
