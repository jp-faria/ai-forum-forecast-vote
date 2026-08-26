# QR Codes

Todos apontam para `https://ai-forum-forecast-vote.vercel.app/`, que redireciona
para a votação. Se a URL da votação mudar, troque o `href` em `index.html` e dê
push: estes QRs continuam valendo e nada precisa ser reimpresso.

| arquivo | uso |
|---|---|
| `qr-preto.svg` | **Gráfica.** Vetor, escala para qualquer tamanho sem perder nitidez. |
| `qr-preto.png` | Impressão rápida. 2048px, preto no branco. |
| `qr-marca.svg` | Peça digital e telão. Navy `#2F418E` no cream `#F8F4EE`. |
| `qr-marca.png` | 2048px, mesma paleta. |
| `qr-marca-logo.png` | Cartaz e story. Athena no centro, 2048px. |

Versão 5, 37x37 módulos, correção de erro **H** (30% do código pode estar
obstruído e ainda lê). É o nível que abre espaço para o logo no centro e o que
sobra de margem para dobra e sujeira num cartaz.

## Tamanho mínimo de impressão

Imprima com pelo menos **2,5 cm** de lado e mantenha a margem branca ao redor,
que já vem nos arquivos. A regra prática é lado maior ou igual a um décimo da
distância de leitura: para alguém escaneando a um metro, 10 cm.

As cinco variantes foram testadas decodificando de volta com o Vision (o mesmo
detector da câmera do iPhone) a 2048, 512, 296 e 148 px. Todas leram.
