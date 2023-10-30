# Automação do Palavra Charada

Este projeto é uma automação para jogar o Palavra Charada e alcançar uma taxa de acerto melhor do que um jogador humano, em um tempo mais curto.

## Endereço para Testes

Você pode testar o projeto no seguinte endereço: [https://charada.vercel.app/](https://charada.vercel.app/)

## Ambiente

- Python 3.12.0
- Jupyter Notebook 6.5.4
- Selenium 4.14.0
- PyAutoGUI 0.9.54
- Unidecode 1.12.0

## Variáveis

- `base`: É uma lista de palavras com 5 letras usadas nas tentativas do jogo. O programa pode inicialmente começar com uma lista vazia e adicionar palavras conforme novas palavras são descobertas. Pode-se usar uma base de palavras pronta. O programa automaticamente acrescenta palavras novas e remove palavras da base caso elas sejam consideradas incorretas no jogo.

- `palavra_base`: São as palavras iniciais para as primeiras tentativas. Os testes mostraram que as palavras 'rosea', 'cupim', 'tango' e 'veloz' têm uma boa eficiência, pois contêm as letras mais frequentes na língua portuguesa e têm as vogais em posições diferentes, facilitando a redução da quantidade de combinações e, portanto, diminuindo o tempo de execução.

## Funções

- `escrevePalavra()`: Separa a palavra em letras e simula o pressionamento de cada uma delas.

- `pegaLetraQueNaoContem()`: Procura pela classe que indica quais letras não estão na palavra e retorna um array com as letras encontradas.

- `pegaLetraNaPosicaoErrada()`: Procura pela classe que indica quais letras estão na palavra e na posição errada e retorna um array com as letras encontradas.

- `retirarLetras()`: Remove as letras que não estão presentes na palavra do alfabeto e retorna as letras que podem estar na palavra.

- `geraVetorLetraFixa()`: Gera um array com as letras que estão na palavra e na posição correta.

- `geraVetorLetraPosicaoErrada()`: Gera um array com as letras que estão na palavra e na posição incorreta. Cada posição pode ter uma ou mais letras.

- `geraArrayComLetrasParaCombinar()`: A partir do array de letras que podem estar em uma determinada posição, retira as letras que podem estar em uma posição errada, diminuindo as letras disponíveis para gerar combinações.

- `geraArrayDeCombinacao()`: Compara o array de letras fixas com o de letras que podem estar na palavra e gera um array com as letras fixas e, caso não existam, inclui as letras que podem estar na palavra.

- `gerarCombinacao()`: Com o array de combinações, gera todas as combinações possíveis de 5 letras com as letras disponíveis.

- `encontrar_palavras_com_letra()`: Compara as palavras geradas nas combinações com a lista da base e retorna todas as palavras presentes na base.

- `compararLista()`: Verifica se as palavras nas listas contêm as letras que estavam fora de posição, eliminando as outras.

