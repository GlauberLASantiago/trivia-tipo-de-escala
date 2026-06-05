# 🎵 Trivia de escalas musicais

Widget de treinamento de percepção musical embutível em qualquer site. Feito com HTML puro + Web Audio API, sem dependências externas.

---

## Como usar

O arquivo é autocontido — basta abrir no navegador.

```bash
open trivia-escalas.html
```

Para embutir em um site existente, copie o conteúdo do `<div class="card">` e do `<script>` para dentro da sua página.

---

## Como funciona

O app toca uma escala aleatória a partir de uma nota fundamental aleatória e o usuário escolhe entre 4 opções qual é o tipo de escala.

- Clique em **ouvir** para escutar a escala
- Escolha entre as 4 opções apresentadas
- Após responder, clique em **outra →** para a próxima questão, que toca automaticamente
- O botão **compartilhar** baixa um `.html` idêntico para enviar por WhatsApp, e-mail ou qualquer canal — e o arquivo gerado também tem o botão de compartilhar

---

## Escalas cobertas

| Escala | Semitons |
|--------|----------|
| Maior | 0 2 4 5 7 9 11 12 |
| Menor natural | 0 2 3 5 7 8 10 12 |
| Menor harmônica | 0 2 3 5 7 8 11 12 |
| Pentatônica maior | 0 2 4 7 9 12 |
| Pentatônica menor | 0 3 5 7 10 12 |
| Blues | 0 3 5 6 7 10 12 |

---

## Timbre — síntese FM

O som é gerado por síntese FM de 2 operadores via Web Audio API:

```
Carrier ratio:      1
Modulator ratio:    14
Modulation index:   1200 (ataque) → decaimento exponencial em 1s
Volume base:        0.25
```

Cadeia de sinal:

```
Modulator OSC → ModGain → Carrier.frequency
Carrier OSC   → AmpGain → Destination
```

---

## Licença

MIT
