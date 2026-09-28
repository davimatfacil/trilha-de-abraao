# Trilha de Abraão

![Trilha de Abraão](screenshot.png)

Jogo de trilha bíblico sobre **Gênesis 12–50**. Os jogadores partem de Ur dos Caldeus e caminham até a terra de Gósen, passando pelas histórias de Abraão, Isaque, Jacó e José.

**▶ Jogar:** https://davimatfacil.github.io/trilha-de-abraao/

## Como jogar

- De 1 a 4 jogadores no mesmo aparelho (computador ou celular).
- Lance o dado e avance pela trilha de 40 casas.
- **Casa `?`**: pergunta de múltipla escolha sobre a era daquela casa. Acertou, ganha 1 ★. Sempre aparece a referência bíblica para leitura.
- **Casa com nome**: um episódio de Gênesis com efeito na partida:
  - avançar: o Chamado (Gn 12), Moriá (Gn 22), a escada de Betel (Gn 28)
  - voltar: a fome (Gn 12), o guisado de Esaú (Gn 25), José vendido (Gn 37)
  - perder a vez: Agar (Gn 16), Labão (Gn 29), a prisão de José (Gn 39)
  - ganhar estrelas: a promessa das estrelas (Gn 15), a luta no Jaboque (Gn 32)
- Quem chega primeiro a Gósen ganha +3 ★ e encerra a jornada. **Vence quem tiver mais estrelas.**

## As quatro eras

| Casas | Era | Capítulos |
|---|---|---|
| 0–14 | Abraão | Gn 12–23 |
| 15–21 | Isaque | Gn 24–27 |
| 22–30 | Jacó | Gn 28–36 |
| 31–39 | José | Gn 37–50 |

## Como foi feito

Um único arquivo `index.html` com HTML, CSS e JavaScript puro. Não usa frameworks, servidor nem banco de dados.

- **Dados separados da lógica**: os objetos `EVENTS` e `QUESTIONS` guardam todo o conteúdo bíblico. Para criar uma trilha de outro livro, basta trocar esses dados.
- **Tabuleiro em serpentina**: `cellPos(i, c)` converte o número da casa em linha/coluna. Linhas pares vão para a direita, ímpares voltam. A grade tem 8 colunas no computador e 5 no celular.
- **Máquina de estados**: `S.phase` (`roll` → `moving` → `card` → `roll`/`over`) controla o que o jogador pode fazer em cada momento.
- **Perguntas sem repetição**: `S.used` registra as perguntas já sorteadas por era.
- **Som sintetizado** com a Web Audio API, sem arquivos de áudio.

## Rodar localmente

Baixe o `index.html` e abra no navegador. Só isso.

## Ideias para próximas versões

- Mais perguntas por era e níveis de dificuldade
- Modo desafio com tempo de resposta
- Casas de versículo para memorizar
- Trilhas de outros livros (Êxodo, Juízes, Atos)

## Autor

Davi · Matemático e estatístico. Projeto pessoal para ensino bíblico com tecnologia.

Referências bíblicas conferidas em Gênesis. As citações são curtas e servem apenas para indicar a leitura.

Código-fonte: https://github.com/davimatfacil/trilha-de-abraao · Licença: [MIT](LICENSE)
