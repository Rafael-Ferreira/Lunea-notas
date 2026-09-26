# 📦 Lunea — Inventário completo do site (26/09/2026)

> Feito pela **Luna** com acesso SSH (somente leitura) na hospedagem Hostinger.
> Complementa [[Lunea — Análise do site (2026-09-26)]] (a análise externa).
> Contexto: o site **não será mais usado** — Rafael vai criar um novo no **Manus/Lovable**.

---

## 🔴 POR QUE O SITE CAIU (causa exata encontrada)

```
Fatal error: Uncaught Elementor\Core\Experiments\Exceptions\Dependency_Exception:
Depending on a hidden experiment is not allowed.
in .../plugins/elementor/core/experiments/manager.php:968
  #1 elementor-pro/core/modules-manager.php(93)
  #2 elementor-pro/plugin.php(350)
```

### O que aconteceu

| Plugin | Versão | Última alteração |
|---|---|---|
| **Elementor (core)** | **4.3.0** | **23/09/2026 18:42** ⚠️ |
| **Elementor Pro** | **3.32.0** | **17/09/2025** (1 ano atrás) |

O **Elementor core se atualizou sozinho** para a 4.3.0 e passou a marcar um
"experimento" como **oculto** — mas o **Elementor Pro 3.32.0** (que não atualiza
desde set/2025, provavelmente por licença vencida) **depende desse experimento**.

➡️ Resultado: erro fatal no carregamento → **HTTP 500 em todo o site**, a partir
de **23/09/2026 à noite**.

**Ou seja: não foi invasão nem corrupção — foi uma atualização automática que
deixou o core e o Pro em versões incompatíveis.**

### Se algum dia quisesse consertar (não é o plano)
Reverter o Elementor core para a 3.x (compatível com o Pro 3.32.0), ou renovar a
licença do Pro, ou desativar o Elementor Pro. **Como o site vai ser aposentado,
não é necessário.**

---

## 📏 Tamanho do site

| Item | Tamanho |
|---|---|
| **Site completo** | **632 MB** |
| `wp-content` (conteúdo) | 519 MB |
| `wp-includes` (core) | 101 MB |
| `wp-admin` | 13 MB |
| — `uploads` (imagens) | **154 MB** |

---

## 📄 Conteúdo existente

| Tipo | Quantidade |
|---|---|
| **Páginas** | **27** |
| Posts do blog | 4 |
| Imagens/anexos | 122 |
| Templates Elementor | 6 |
| Formulários | 1 (*"Formulário Home"* — Contact Form 7) |
| Usuários | 1 (`contato@lunea.com.br`) |

### As 27 páginas (títulos)

**Institucional / serviços**
- Início (`inicio`) · Blog · Portfólio · Área · demonstração
- Política de Privacidade (×2) · Termos de Serviço · Termo de Uso

**Produtos/serviços Lunea**
- **Dispara** · Dispara - Lunea MKT · Dispara Cardápio · Dispara Cursos Livres
- Disparador Ecompo · ECOMPO
- **Agente de IA - Prompts** · App Obras · Raspador · template logica atend

**Nichos / landing pages**
- **Escritório de Advocacia com IA** · Landing Pages para Advocacia
- Portfólio Landing Pages
- Radio (×2) · Sorteio Copa do Mundo 2026

**Clientes/materiais**
- Prompt O Papo de Intercâmbio · Script de Vendas do Papo de Intercâmbio

### Os 4 posts do blog
1. Otimizado para móveis com diretrizes AMP (2025)
2. Dicas e ferramentas para um portfolio profissional
3. Landing Page: O Segredo Para Alta Conversão e Sucesso
4. Como Criar um ETL Inteligente com Python e IA para Limpar Dados Antes do Banco

---

## 🖼️ Imagens (o acervo visual)

| Item | Valor |
|---|---|
| Total de arquivos | **1.250** |
| Tamanho | **154 MB** |

**Por formato:** 753 `webp` · 263 `png` · 72 `jpg` · 34 `jpeg` · 65 `woff2` + fontes (woff, ttf, eot)

**Por ano:** 2023 → 80 · 2024 → 0 · **2025 → 856** · 2026 → 190

> 💡 A maioria está em **webp** (já otimizado) — ótimo para reaproveitar no site novo.

---

## 🧩 Plugins ativos (15)

| Plugin | Para que servia |
|---|---|
| `elementor` + `elementor-pro` | construtor das páginas |
| `wordpress-seo` (Yoast) | SEO |
| `litespeed-cache` | cache |
| `contact-form-7` + `wpforms-lite` | formulários |
| `insert-headers-and-footers` | scripts no head/rodapé |
| `custom-css-js` | CSS/JS extra |
| `happy-elementor-addons` · `ht-mega-for-elementor` · `htmega-pro` · `ht-menu` | addons do Elementor |
| `bit-integrations` | integrações |
| `omnisend` | e-mail marketing |
| `full-customer` | CRM/leads |

**Tema:** `hello-elementor`

---

## ⚙️ Ambiente

| Item | Valor |
|---|---|
| WordPress | **7.1.2** |
| PHP | 8.1.34 |
| Idioma | pt_BR |
| Nome do site | **Lunea** — *"Serviços Digitais"* |
| URL configurada | ⚠️ **`http://lunea.com.br`** (sem HTTPS!) |

> ⚠️ O site estava configurado em **http://** mesmo tendo certificado SSL —
> vale não repetir esse erro no site novo (redirecionamento + SEO).

---

## 🎯 O que vale levar para o site novo

| O que | Vale? | Onde está |
|---|---|---|
| **Textos das 27 páginas** | ✅ sim | banco (exportável) |
| **Posts do blog** | ✅ sim (4) | banco |
| **Imagens** | ✅ sim (154 MB) | `wp-content/uploads/` |
| **Formulário "Home"** | ✅ recriar | CF7 |
| Tema / plugins | ❌ não | — |
| Estrutura do WordPress | ❌ não | — |

---

## 🖥️ Infraestrutura

| Item | Valor |
|---|---|
| Conta Hostinger | `u529990366` |
| Servidor | `br-asc-web1078.main-hosting.eu` |
| SSH | `62.72.62.17:65002` (chave `id_hostinger_lunea`) |
| Diretório do site | `~/domains/lunea.com.br/public_html` |
| Outros domínios na conta | 29 |

---

## 💡 Conclusões para o site novo

1. **O site novo (estático, do Lovable/Manus) não sofre esse tipo de queda** —
   não tem plugin que se auto-atualiza nem PHP para quebrar
2. **Os textos e as imagens valem muito** — 27 páginas de conteúdo + 1.250 arquivos já otimizados
3. **Não precisa consertar o WordPress** para recuperar o conteúdo — os arquivos e o banco estão intactos
4. **A hospedagem fica** (pelo e-mail) — só trocar o conteúdo de `public_html` pelo build novo
5. **Não esquecer:** MX, SPF e Brevo **não devem ser tocados**

---

*Inventário feito por SSH (somente leitura) em 26/09/2026. Ver também [[Lunea — Análise do site (2026-09-26)]].*
