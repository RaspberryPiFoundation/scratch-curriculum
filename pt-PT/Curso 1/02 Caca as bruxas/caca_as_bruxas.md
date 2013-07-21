Nível 1

# Caça às bruxas

__Introdução:__
Neste jogo deves caçar as bruxas que aparecem no ecrã. Ganhas pontos sempre que
acertares numa delas. O objetivo é obter o máximo de pontos possível em 30
segundos!

## PASSO 1: Criar uma bruxa voadora

1. Crie um novo projecto Scratch.

2. Remove o actor gato e substitui o cenário existente pelo cenário
«Natureza/woods», mudando-lhe o nome para «bosque».

3. Cria um novo actor, clicando no ícone «Escolher actor a partir da biblioteca»
à direita de «Novo actor» e escolhendo o actor Fantasia/Witch», mudando-lhe o
nome para «a bruxa». Agora, queremos que a nossa bruxa se mova.

4. Cria uma variável chamada «a velocidade», seleccionando a opção «Apenas para
este actor». No monitor desta variável que surge no palco deve estar escrito «a
bruxa a velocidade». Se estiver escrito apenas «a velocidade», remova a variável
e crie-a de novo, seleccionando «Apenas para este actor». Desmarca a caixa de
selecção ao lado do bloco «a velocidade» na paleta «Dados» para que o seu
monitor não apareça no palco. Usaremos esta variável para controlar a velocidade
da bruxa à medida que o jogo decorre.

5. Queremos que a bruxa comece a mexer quando o jogo começar. Para isso, depois
de seleccionar o actor «a bruxa», crie o seguinte guião:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	altera [a velocidade ▼] para [5]
	repete para sempre,
		anda (a velocidade) passos
	[fim do comando «repete para sempre»]
	[fim do guião]
```
		
### Testa o teu projecto

__Clica na bandeira verde__ e vê o que a bruxa faz. Por que razão fica encravada
na borda do palco?

6. Para a bruxa não ficar encravada, precisamos que ela dê meia volta quando
bater na borda do palco. Melhor, precisamos que _ressalte_ na borda do palco.
Sob o comando [anda (a velocidade) passos], adiciona um  comando [se estiveres a
bater na borda, ressalta]:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	altera [a velocidade ▼] para [5]
	repete para sempre,
		anda (a velocidade) passos
		se estiveres a bater na borda, ressalta
	[fim do comando «repete para sempre»]
	[fim do guião]
```
		
7. Para evitar que a bruxa fique de cabeça para baixo, clica no botão azul com
um «i» no canto superior esquerdo do ícone que representa «a bruxa» e escolhe o
estilo de rotação «olha apenas para a esquerda e para a direita».

### Testa o teu projecto

__Clica na bandeira verde.__ A bruxa move-se de um lado para o outro
atravessando todo o palco?

__Para parar, carrega no sinal de _stop_.__

### Coisas a experimentar

__Experimenta alterar o valor da variável «a velocidade» para fazer a bruxa
voar mais depressa ou mais devagar.__

__Como farias para que a bruxa fosse acelerando ao longo do tempo?__ (Este
desafio é difícil, por isso não te preocupes se não descobrires uma solução.
Terás mais pistas à medida que trabalhas neste projecto.)

## PASSO 2: Fazer a bruxa aparecer e desaparecer aleatoriamente

Para tornar o jogo mais divertido, vamos fazer a bruxa aparecer e desaparecer
aleatoriamente. Para isso, vamos criar um guião que é executado ao mesmo tempo
que o guião que faz a bruxa mexer. Este novo guião precisa de esconder a bruxa
durante um período de tempo aleatório e depois mostrá-la também durante um
período de tempo aleatório, repetindo esta sequência para sempre (ou até que o
jogo acabe). Cria o seguinte guião para a bruxa:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		esconde-te
		espera (um valor ao acaso entre (2) e (5)) s
		mostra-te
		espera (um valor ao acaso entre (3) e (5)) s
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ A bruxa move-se de um lado para o outro,
atravessando todo o palco, e desaparecendo e aparecendo aleatoriamente?

### Coisas a experimentar

__Tenta alterar as gamas dos números aleatórios. O que acontece se escolheres
números muito grandes ou números muito pequenos?__ (Será que isto te dá pistas
sobre como fazer a bruxa acelerar com o decorrer do jogo?)

## PASSO 3: Fazer a bruxa desaparecer ao ser clicada

Para transformar o projecto num jogo, precisamos de dar alguma coisa que fazer
ao jogador. O jogador precisará de clicar na bruxa para a fazer desaparecer.
Quando a bruxa for clicada, queremos que desapareça e que toque um som.

1. No separador «Sons» da bruxa, remove o som «pop» e escolhe um novo som a
partir da biblioteca, nomeadamente o som «Electrónicos/fairydust». Altera o nome
desse novo som para «pó de fadas».

2. Adiciona este guião à bruxa:

```scratch
	Quando alguém clicar em ti
	esconde-te
	toca o som [pó de fadas ▼]
	[fim do guião]
```
		
### Testa o teu projecto

__Clica na bandeira verde.__ A bruxa desaparece e toca o som pretendido quando
lhe clicas?

##PASSO 4: Adicionar pontuação e um cronómetro

Temos uma bruxa, mas queremos é fazer um jogo! Queremos pontuar sempre que
clicarmos na bruxa, mas também que o jogo tenha uma duração limitada. Podemos
usar variáveis, tanto para a pontuação, como para o cronómetro.

1. Cria uma nova variável, para todos os actores, chamada «a pontuação». Altera
o guião da bruxa para adicionar um a esta variável sempre que ela for clicada.

```scratch
	Quando alguém clicar em ti
	esconde-te
	toca o som [pó de fadas ▼]
	adiciona a [a pontuação ▼] o valor (1)
	[fim do guião]
```
	
2. Cria uma nova variável, para todos os actores, chamada «o tempo disponível».
Adiciona ao palco um guião que, quando a bandeira verde for clicada, inicializa
as variáveis que criaste, i.e., atribui o valor 30 a «o tempo disponível» e o
valor 0 à pontuação. Depois dessas inicializações, usamos um comando [até que
<>, repete] para ir esperando um segundo e reduzindo em uma unidade o valor da
variável «o tempo disponível» até que o tempo disponível se esgote, ou seja, até
que o valor da variável «o tempo disponível» se torne 0, altura em que usamos o
comando [pára [tudo ▼]] para parar o jogo:
	
```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	altera [o tempo disponível ▼] para [30]
	altera [a pontuação ▼] para [0]
	até que <[o tempo disponível] = [0]>, repete
		espera (1) s
		adiciona a [o tempo disponível ▼] o valor (-1)
	[fim do comando «até que repete»]
	pára [tudo ▼]
	[fim do guião]
```

3. Carrega no botão direito do rato sobre o monitor da variável «a pontuação» e
escolhe «visor grande». Depois, arruma esse monitor no canto superior esquerdo
do palco.

4. Faz o mesmo para o monitor da variável «o tempo disponível», arrumando-o no
canto superior direito do palco.

### Testa o teu projecto

__Clica na bandeira verde.__

### Coisas a experimentar

__Como farias para acelerar a bruxa à medida que o tempo passa?__

__Parabéns, terminaste o jogo básico! No entanto, há mais coisas a fazer no teu
jogo. Aceita este desafio!__

## DESAFIO: Adicionar mais bruxas

Se o jogo com uma bruxa é bom, com várias bruxas deve ser ainda melhor! Vamos
criar pôr três bruxas a esvoaçar por aí.

1. Clica o botão direito do rato sobre a bruxa, na área «Actores», e escolhe
«duplicar» para duplicares a bruxa. Repete o processo para criares a terceira
bruxa. Podes dar nomes próprios a cada bruxa. Por exemplo, «a Josefina».

2. Selecciona cada uma das bruxas na área «Actores» e ajusta o tamanho de cada
uma delas, de modo a que todas tenham tamanhos diferentes.

3. Para cada bruxa, altera a variável «a velocidade» de modo a que cada bruxa
voe a uma velocidade diferente da velocidade das restantes.

4. Altera a posição das bruxas no palco de modo a que não se sobreponham
demasiado. Experimenta colocar as bruxas mais pequenas mais acima no palco e
dar-lhes uma velocidade menor: quando mais pequena, mais acima e mais devagar.
Deixa que elas se sobreponham parcialmente. Verás que parece haver profundidade
no jogo.

### Testa o projecto

__Clica na bandeira verde.__ Vês três bruxas que se movem de um lado para o
outro, atravessando todo o palco, e desaparecendo e aparecendo aleatoriamente?
As bruxas desaparecem e tocam o som pretendido quando lhes clicas? O jogo pára
ao fim de 30 segundos? A pontuação é actualizada, quando apanhas uma bruxa?

### Coisas a experimentar

1. Qual a quantidade adequada de bruxas para este jogo?

2. Consegues dar aparências diferentes à bruxas? Tanto podes editar os seus
trajes como podes usar comandos da paleta «Aparência».

3. Consegues fazer as bruxas valerem pontos diferentes? Que tal atribuir mais
pontos às bruxas mais pequenas ou mais velozes?

__Parabéns, terminaste! Desfruta o teu novo jogo!__

Não te esqueças que podes partilhar o teu jogo com todos os Scratchadores
carregando no botão «Partilha»!