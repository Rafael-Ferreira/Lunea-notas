# 🤖 Cofre da Luna

Este cofre é sincronizado via **Obsidian Git** com o repositório privado
`Rafael-Ferreira/Lunea-notas`.

## Como funciona

- **Rafael** escreve no Obsidian (PC ou celular) → dá *commit/push* → a **Luna** dá *pull* e lê
- **Luna** escreve aqui → dá *push* → Rafael dá *pull* no Obsidian e vê

> ⚠️ Antes de escrever, a Luna **sempre dá `pull`** primeiro, para não sobrescrever
> o que o Rafael editou no Obsidian.

## Setup (feito em 26/09/2026)

| Item | Valor |
|---|---|
| Repositório | `git@github.com:Rafael-Ferreira/Lunea-notas.git` |
| Chave SSH | `/opt/data/.ssh/id_github_obsidian` (deploy key com escrita) |
| Cópia local (servidor) | `/opt/data/obsidian-vault` |
| Variável | `OBSIDIAN_VAULT_PATH=/opt/data/obsidian-vault` |

## O que a Luna pode fazer aqui

- Ler e buscar em todas as notas
- Criar e editar notas (com wikilinks `[[assim]]`)
- Salvar relatórios e inventários direto no cofre

## Regras do cofre

- 🔒 **Nada de senha, token ou chave** dentro das notas
- 📎 Anexos (imagens) funcionam, mas cuidado com o tamanho
- 🏷️ Usar wikilinks para ligar notas relacionadas

---

*Nota criada pela Luna para validar a sincronização.*
