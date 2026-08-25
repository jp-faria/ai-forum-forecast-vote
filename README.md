# Vote no AI Forum Forecast

Página de destino do QR Code da votação. Uma tela, um botão, e o redirecionamento para a
página oficial de votação. Sem login, sem backend, sem build.

Ela carrega a identidade visual do [AI Forum Forecast](https://github.com/jp-faria): as mesmas
cores (cream `#F8F4EE`, navy `#2F418E`), as mesmas fontes (Lora e Inter, self-hosted), o mesmo
botão pill e a mesma orb neural do hero.

## Trocar a URL de votação

Abra `index.html`, procure `__VOTE_URL__` e substitua pela URL oficial. Ela aparece em um
lugar só, no `href` do botão:

```html
<a class="cta" href="__VOTE_URL__" rel="noopener">Votar agora</a>
```

Um `git push` na `main` publica a alteração, a Vercel refaz o deploy sozinha.

## Rodar local

```bash
python3 -m http.server 8000
```

Depois abra http://localhost:8000. Não há passo de build: o que está no repositório é o que
vai para o ar.

## Deploy na Vercel

1. Em https://vercel.com/new, escolha Import Git Repository e selecione este repositório.
2. Em Framework Preset, deixe **Other**. Build Command e Output Directory ficam vazios.
3. Deploy.

O `vercel.json` cuida do cache dos assets (um ano, imutável) e das URLs sem extensão.

## Estrutura

```
index.html                  a página inteira, CSS incluído
assets/
  forecast-logo.png         logo do Forecast
  favicon-32.png            ícone da aba
  apple-touch-icon.png      ícone da tela inicial do iOS
  og-image.jpg              card de compartilhamento, 1200x630
  fonts/                    Lora 400, Lora 400 italic, Inter variável
vercel.json
```

Peso total da primeira visita: cerca de 145 KB, dos quais 108 KB são as fontes, carregadas com
`font-display: swap` e portanto fora do caminho do primeiro paint.

## Acessibilidade e desempenho

O botão tem 60 px de altura, acima do mínimo de 44 px para alvo de toque. O texto cream sobre
o navy da marca dá 8,04:1 de contraste. A página respeita `prefers-reduced-motion`, zerando
duração e delay das animações. Zero JavaScript, então nada quebra com o script bloqueado.
