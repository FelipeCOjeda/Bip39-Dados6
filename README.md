# BIP39 com Dados de 6 Lados

Gere seeds BIP39 seguras usando dados comuns de 6 lados e a wordlist oficial BIP39 (2.048 palavras).

## Por que usar dados?

A seed BIP39 protege seus bitcoins. Gerá-la com dados físicos garante que **você** controla a aleatoriedade — sem depender de software ou internet.

## Como funciona

### Passo a passo

1. Jogue **5 dados** de uma vez (ou 1 dado 5 vezes).
2. Anote os números na ordem em que aparecem (ex: 5-3-6-4-1 → `53641`).
3. Converta o código para um índice de 0 a 7775.
4. Se o índice ≥ 6144, **jogue novamente** (~21% dos casos).
5. Se válido, o índice mod 2048 aponta para a palavra BIP39.
6. Repita para **12 palavras** (128 bits) ou **24 palavras** (256 bits).

### Por que 5 dados?

Um dado tem 6 faces. Cinco dados dão 6⁵ = **7.776 combinações**. Como BIP39 tem 2.048 palavras, usamos os primeiros 6.144 códigos (2.048 × 3) — cada palavra aparece exatamente 3 vezes, sem viés. Os 1.632 códigos restantes são descartados.

### Checksum

A última palavra de uma seed BIP39 (a 12ª ou a 24ª) contém bits de checksum. Ela **não deve ser sorteada** — deve ser calculada a partir das palavras anteriores. Use uma ferramenta offline (ex: Ian Coleman) para determinar a última palavra.

### Resistência

| Palavras | Entropia | Uso |
|---|---|---|
| 12 | 128 bits | Seed BIP39 padrão |
| 24 | 256 bits | Seed BIP39 alta segurança |

Cada palavra adiciona 11 bits (log₂ 2048).

## O que tem neste repositório

- `tabela_bip39_dados.xlsx` — Planilha com consulta interativa (dropdowns para os 5 dados) e mapa completo dos 7.776 códigos.
- `diceware_dados6_offline.html` — Calculadora offline com consulta de dados, coleção de palavras, e avaliação de entropia (nota 0-10).
- `tabela_diceware_bip39_1pagina.pdf` — Tabela de página única com todos os 7.776 códigos mapeados para palavras BIP39.

## Dicas de segurança

- **A ordem importa** — não reordene as palavras para "soar melhor". É parte da aleatoriedade.
- **Use dados de qualidade** — se duvida do balanceamento, use dados de cassino (arestas vivas).
- **Tudo offline** — role, anote no papel, busque na lista impressa ou no HTML sem internet.
- **12 palavras → nenhuma repetição.** 24 palavras → máximo 1 repetição.
- **Nunca reutilize** — uma seed publicada (como qualquer exemplo) já não serve.
- **Guarde offline** — jamais digite a seed completa em um dispositivo conectado.

## Fonte da wordlist

Lista oficial BIP39 English: [github.com/bitcoin/bips](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt)

## Licença

MIT
