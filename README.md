# BIP39 com Dados de 6 Lados

Gere seeds BIP39 seguras usando dados comuns de 6 lados e a wordlist oficial BIP39 (2.048 palavras, 10 idiomas).
Tutorial: https://youtu.be/cYcH_BWVgdQ

## Por que usar dados?

A seed BIP39 protege seus bitcoins. Gerá-la com dados físicos garante que **você** controla a aleatoriedade — sem depender de software ou internet.

## Como funciona

### Passo a passo

1. Jogue **5 dados** de uma vez (ou 1 dado 5 vezes).
2. Anote os números na ordem em que aparecem (ex: 5-3-6-4-1 → `53641`).
3. Converta o código para um índice de 0 a 7775.
4. Se o índice ≥ 6144, **jogue novamente** (~21% dos casos).
5. Se válido, o índice mod 2048 aponta para a palavra BIP39.
6. Repita para **11 palavras**.
7. A **12ª palavra** é checksum — use a calculadora do HTML para determiná-la.

### Por que 5 dados?

Um dado tem 6 faces. Cinco dados dão 6⁵ = **7.776 combinações**. Como BIP39 tem 2.048 palavras, usamos os primeiros 6.144 códigos (2.048 × 3) — cada palavra aparece exatamente 3 vezes, sem viés. Os 1.632 códigos restantes são descartados.

### Idiomas disponíveis

English, Español, Français, Italiano, Português, Čeština, 日本語, 한국어, 简体中文, 繁體中文

### Checksum

A última palavra de uma seed BIP39 (a 12ª ou a 24ª) contém bits de checksum. Ela **não deve ser sorteada** — deve ser calculada. O HTML offline inclui calculadora de checksum com SHA-256.

### Entropia

| Palavras | Entropia | Uso |
|---|---|---|
| 12 | 128 bits | Seed BIP39 padrão |
| 24 | 256 bits | Seed BIP39 alta segurança |

Cada palavra adiciona 11 bits (log₂ 2048).

## O que tem neste repositório

- `tabela_bip39_dados.xlsx` — Planilha multilíngue com consulta interativa e mapa de 7.776 códigos → índices BIP39.
- `diceware_dados6_offline.html` — Calculadora offline com 10 idiomas, entropia 0-10 e cálculo de checksum SHA-256.
- `tabela_diceware_bip39_1pagina.pdf` — Tabela de página única com as 2.048 palavras BIP39 (English).

## Dicas de segurança

- **A ordem importa** — não reordene as palavras.
- **Use dados de qualidade** — se duvida do balanceamento, use dados de cassino (arestas vivas).
- **Tudo offline** — role, anote no papel, busque na lista impressa ou no HTML sem internet.
- **12 palavras → nenhuma repetição.** 24 palavras → máximo 1 repetição.
- **A 12ª (ou 24ª) palavra é checksum** — não sorteie, calcule.
- **Guarde offline** — jamais digite a seed completa em um dispositivo conectado.

## Fonte da wordlist

Lista oficial BIP39: [github.com/bitcoin/bips](https://github.com/bitcoin/bips/blob/master/bip-0039)

## Licença

MIT
