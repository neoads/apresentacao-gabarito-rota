# Apresentação Comercial Gabarito · v3

Deck HTML de 44 slides (copy travada, igual à v2) redesenhado em 2026-09-02 com:

- **Design system do site gabaritoedu.com.br:** Bebas Neue (display) + Raleway (texto), navy `#0a1630` / `#193c6f`, azul `#96befb`, amarelo `#fcc331`, botão gradiente azul do site, cards de vidro com raio 22px.
- **Estilo de slides da referência "APT PROGRAMA - FULL SALES":** fundo de rede de nós + hexágonos, anel de hexágonos nos riscos, roda do sistema (Ciclo ROTA), escada, pontos numerados, barra de economia 1D/30D, slide dividido de preço, selo de garantia, mockups de notebook/tablet.
- Logo GABARITO EDU (check amarelo) em todos os slides, mascote coruja na capa/fechamento.

## Abrir

```powershell
python -m http.server 4177 --bind 127.0.0.1
```

Depois acesse `http://127.0.0.1:4177/`. Setas, PageUp/Down e espaço navegam.

Pra capturar um slide isolado (print/QA): `http://127.0.0.1:4177/?static=1&slide=15`.

## Arquivos

- `index.html`: versão v3 (atual)
- `index-v2-gpt.html`: versão anterior feita pelo GPT
- `index-original.html`: versão publicada antes da v2
- `assets/`: fotos, mockups, selo, mascote
- `.codex-img-order.md`: ordem pronta pro Codex fazer upscale 2x das fotos de aula e mascote sem fundo

## Pendências

1. **Upscale das fotos de aula** (`aula-01/03/04/07.png` têm ~410px). Hoje elas são exibidas em tamanho próximo do nativo pra não borrar. Quando a cota do Codex voltar, rodar na raiz desta pasta:

```powershell
Get-Content -Raw ".codex-img-order.md" | codex exec -C "." --sandbox workspace-write -c sandbox_workspace_write.network_access=true --skip-git-repo-check -
```

Depois trocar os `src` de `assets/aula-0X.png` por `assets/hd/aula-0X.png` nos slides 03 e 06, e `mascote-gabarito.jpg` por `assets/hd/mascote-transparente.png` na capa (slide 01) e fechamento (44).

2. Slides 04 e 05 seguem com o espaço reservado (mockup de celular) pra boletim / print de evolução real.
