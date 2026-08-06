# Passphrase Diceware com Dados de 6 Lados

Gere passphrases seguras usando dados comuns de 6 lados e a wordlist oficial da EFF (7.776 palavras).

## Por que usar dados?

A passphrase protege sua seed BIP39 com uma camada extra de segurança. Gerá-la com dados físicos garante que **você** controla a aleatoriedade — sem depender de software ou internet.

## Como funciona

### Passo a passo

1. Jogue **5 dados** de uma vez (ou 1 dado 5 vezes).
2. Anote os números na ordem em que aparecem (ex: 5-3-6-4-1 → `53641`).
3. Procure o código de 5 dígitos na planilha ou no HTML offline.
4. A palavra correspondente é parte da sua passphrase.
5. Repita para ter **5-6 palavras** (recomendado: 6 palavras).

### Por que 5 dados?

Um dado tem 6 faces. Cinco dados dão 6⁵ = **7.776 combinações**, exatamente a quantidade de palavras da lista EFF. Cada jogada aponta para uma palavra única, sem sobrar nem faltar.

### Exemplo

| Jogada | Código | Palavra |
|---|---|---|
| ⚄⚂⚅⚃⚀ | 53641 | shaky |
| ⚃⚃⚅⚃⚁ | 44642 | pork |
| ⚃⚃⚅⚀⚃ | 44614 | polygon |
| ⚃⚁⚄⚀⚃ | 42514 | oozy |
| ⚂⚃⚅⚅⚀ | 34661 | jalapeno |
| ⚀⚅⚀⚀⚅ | 16116 | clause |

**Passphrase: shaky pork polygon oozy jalapeno clause**

### Resistência

| Palavras | Entropia | Resistência |
|---|---|---|
| 5 | ~64 bits | Centenas de anos |
| 6 | ~77 bits | Milhares de anos |
| 7 | ~90 bits | Milhões de anos |
| 8 | ~103 bits | Bilhões de anos |

Cada palavra adiciona ~12.9 bits (log₂ 7776).

## O que tem neste repositório

- `tabela_diceware_eff.xlsx` — Planilha com consulta interativa (dropdowns para os 5 dados) e mapa completo dos 7.776 códigos.
- `diceware_dados6_offline.html` — Calculadora offline com consulta de dados, coleção de palavras, e avaliação de entropia (nota 0-10).

## Dicas de segurança

- **A ordem importa** — não reordene as palavras para "soar melhor". É parte da aleatoriedade.
- **A lista é pública** — seu poder não está em ocultá-la, está no fato de que a tirada saiu dos seus dados.
- **Use dados de qualidade** — se duvida do balanceamento, use dados de cassino (arestas vivas).
- **Tudo offline** — role, anote no papel, busque na lista impressa ou no HTML sem internet.
- **Passphrase ≠ seed** — guarde a passphrase **separada** da sua seed phrase.
- **Nunca reutilize** — uma passphrase publicada (como o exemplo acima) já não serve.

## Fonte da wordlist

Lista oficial da EFF (Electronic Frontier Foundation): [eff.org/dice](https://www.eff.org/dice)

## Licença

MIT
