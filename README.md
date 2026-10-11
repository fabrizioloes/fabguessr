# FabGuessr

Painel com o meu histórico de GeoGuessr, round a round, desde outubro de 2025. Serve para ver em que
países e regiões eu erro e como isso muda com o tempo.

**Link:** https://fabrizioloes.github.io/fabguessr/

## O que tem no painel

- **Mapa.** O mundo pintado pela taxa de acerto de cada país. Tocar num país desce para ele, e tocar
  numa partida mostra cada round com o local certo e o meu palpite.
- **Partidas.** A lista por dia e o detalhe de cada uma.
- **Erros.** Os países que eu confundo entre si, o acerto por país e por região, e a distância dos
  palpites.
- **Evolução.** Pontos, acerto, rating e volume de jogos por dia, semana ou mês.
- **Rounds.** A tabela completa, ordenável.

Os filtros (período, tipo de jogo, modo, resultado, mapa e país) valem para todas as páginas e ficam guardados no
navegador. O painel foi pensado para funcionar bem no celular.

## De onde vêm os dados

Os duelos (1v1 e 2v2) e as partidas clássicas são lidos da API do próprio GeoGuessr, numa sessão
logada. Um script em R junta as coletas sem duplicar, identifica país e região de cada local e de
cada palpite com o Natural Earth, e gera o `dados.js` que o painel lê.

Oponentes e parceiros de 2v2 não são identificados. Deles fica só o rating.

## O que tem neste repositório

Só o que o GitHub Pages publica.

| Arquivo | O que é |
|---|---|
| `index.html` | O painel inteiro, em HTML, CSS e JavaScript, com mapas em d3 |
| `dados.js` | Os rounds já processados, gerado pelo R. Não se edita à mão |

O coletor, o script R e os dados brutos ficam fora daqui. O histórico de commits é curto de
propósito, porque cada atualização de dados substitui o commit `Dados` anterior.
