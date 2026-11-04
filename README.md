# Orivox

**Orivox** é uma plataforma de música gratuita que roda 100% no navegador — sem servidor, sem cadastro e sem nada saindo do seu computador. Mixe pistas, gere partituras e ouça as composições do projeto **Canções do Altar**, de Raphael Silveira.

🔗 **No ar:** https://orivoxstudio10.github.io/orivoxstudio/
📦 **Versão:** v2.5

---

## Páginas

| Página | O que faz |
|---|---|
| **`index.html`** — Player Multipista | Carrega várias pistas de áudio, mixa (volume, pan, mudo, solo), separa pistas, mostra **acordes (beta)** e um **metrônomo visual** que acompanha o andamento real da música. Exporta o mix. |
| **`partitura.html`** — Partitura | Transforma áudio em partitura em 2 passos: envia o áudio ao **caderno Orivox** (no Google Colab) e importa de volta o arquivo gerado (**MusicXML, MIDI ou PDF**) para visualizar na própria página, com **acompanhamento sincronizado** (cursor e destaque seguindo o som). Exporta em XML/MIDI/PDF. |
| **`composicoes.html`** — Canções do Altar | Reúne as composições autorais de Raphael Silveira, direto do **YouTube** e do **SoundCloud**. |

As páginas se conectam: o Player Multipista leva à Partitura e às Composições, e todas têm o botão **"Voltar ao estúdio"**.

---

## O caderno (Google Colab)

A transcrição de áudio em partitura de alta qualidade usa GPU, o que uma página estática não consegue fazer sozinha. Por isso o Orivox usa um **caderno no Google Colab** (gratuito):

- A página **Partitura** abre o caderno já pronto no Colab e, depois, importa o arquivo que ele gera.
- A **Célula 8** gera a partitura completa; a **Célula 9** gera a cifra (acordes + letra) em PDF.
- O caderno também pode ser baixado direto pela página Partitura (botão **"Baixar o caderno (.ipynb)"**).

---

## Como usar

**Mixar e ver acordes:** abra `index.html`, arraste suas pistas, ajuste o mix, use o metrônomo visual e a aba de acordes.

**Gerar partitura:**
1. Em `partitura.html`, envie o áudio — o caderno abre no Colab numa nova aba.
2. No Colab, rode a **Célula 8** (marque `ENVIAR_AUDIO_AGORA`, envie o áudio) e baixe o **MusicXML** (ou MIDI/PDF).
3. De volta ao Orivox, **importe** o arquivo gerado: a partitura aparece na própria página, com acompanhamento sincronizado.

---

## Tecnologia

Tudo roda no navegador, com bibliotecas abertas:

- **Áudio e mixagem:** Web Audio API
- **Detecção de notas e acordes:** modelos de IA executados no próprio navegador
- **Notação musical:** renderização de MusicXML em partitura
- **Som:** reprodução de MIDI com banco de sons (soundfont)
- **Fontes:** Fraunces, Inter, IBM Plex Mono

O caderno (Colab) faz a transcrição com GPU (separação de pistas, detecção de notas, reconhecimento de letra e gravação da partitura).

---

## Créditos

Desenvolvido por **Raphael Silveira**. Projeto **Canções do Altar**.
Código das páginas: aberto. Os modelos de IA utilizados seguem as licenças de seus respectivos autores (uso não comercial quando aplicável).
