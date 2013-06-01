Level 1

#Caça às bruxas

__Introdução:__
Você ganha pontos acertando as bruxas que aparece na tela. O objetivo é ganhar o máximo de pontos em 30 segundos!

##PASSO 1: Crie uma bruxa voadora

1. Crie um novo projeto scratch.
2. Apague o sprite do gato e substitua a imagem de fundo com a imagem de natureza/bosque.
3. Use o botão "Escolha um sprite do arquivo" para adicionar ao projeto um novo sprite de bruxa (selecione fantasy/witch1). 

Agora queremos que a nossa bruxa se mexa

4. Adicione uma variável chamada velocidade somente para este objeto.
No Palco, no monitor de palco para esta variável deve aparecer “objeto1 velocidade”.
Se aparecer apenas “velocidade”, apague a variável e crie-a de novo selecionando "somente para este objeto".
Desmarque a caixa ao lado do bloco velocidade no quadro de variáveis de modo que ela não apareça no Palco.
A variável velocidade vai controlar a velocidade com que a bruxa se mexe. Nós usamos uma variável para que possamos mudar a velocidade a bruxa se mexe durante o jogo.
5. Nós queremos que a bruxa comece a se mexer quando o jogo comece, entao faça un script como esse:

```scratch

  when FLAG clicked

	set speed to 5

	forever

		move speed steps

	(end forever)
```
		
###Teste seu projeto
__Clique na bandeira verde__ e olhe o que a bruxa faz. Por que ela fica trancada no canto da tela ?

6. Para evitar que a bruxe fique trancada nós precisamos fazê-la ir para o outro lado quando ela atinge o canto da tela. Abaixo do bloco de passos, adicione um if no canto, recocheteie.


```scratch

	when FLAG clicked

	set speed to 5

	forever

		move speed steps

		if on edge, bounce

	(end forever)
```
7. Para evitar que a bruxa fique de cabeça para baixo, clique  __only face left-right button__ in the Sprite Summary area.

###Teste o seu projeto
__Clique na bandeira verde.__ 
A bruxa se mexe de um lado a outro atravessando a tela?

Salve o seu projeto

###Coisas para tentar
__Tente mudar o valor da variável velocidade para fazê-la voar mais rápido ou mais lentamente.__

__Como você faria a bruxa acelerar mais em função do tempo que ela voa?__
(Esta é uma pergunta difícil, mas não se preocupe se você nao consegue ver como fazê-lo. Você terá mais dicas enquanto voce trabalha neste projeto.)

##PASSO 2: Faça a bruxa aparecer e desaparecer de maneira aleatória

Para tornar o jogo mais divertido, nós queremos que a bruxa apareça e desapareça de modo aleatório. Faremos isso com um outro script que é executado ao mesmo tempo que o script que faz a bruxa se mexer. Este novo script precisa esconder a bruxa durante um tempo aleatório, então fazê-la aparecer durante um tempo aleatório, e repetir isso para sempre (ou até que o jogo acabe).

Crie este script para a bruxa:

```scratch

	when FLAG clicked

	forever

		hide

		wait pick random 2 to 5 secs

		show

		wait pick random 3 to 5 secs

	(end forever)
```

###Teste o seu projeto
__Clique na bandeira verde.__ 
A bruxa se mexe de um lado a outro atravessando a tela, desaparecendo e aparecendo aleatoriamente ?

Salve o seu projeto

###Coisas para tentar
__Tente mudar os valores aleatórios. O que acontece se você escolher números muito grandes ou muito pequenos ?__
(Isto dá pistas sobre como fazer a bruxa acelerar mais de acordo com a duração do jogo?)

##PASSO 3: Faça a bruxa desaparecer quando ela é clicada

Para transformar isso em um jogo, precisamos que o jogador faça algo. Eles precisam clicar na bruxa para que ela desapareça. Quando a bruxa é clicada queremos que ela desapareça e que seja tocado um som.

1. No tab de Sons, importe o som electronic/fairydust. 

2. Adicione este script para a bruxa:

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust
```
###Teste o seu projeto
__Clique na bandeira verde.__

A bruxa desaparece e toca um som quando é clicada ?

Salve o seu projeto

##Passo 4: Adicione um score e um cronometro

Nós temos uma bruxa, mas agora nós queremos fazer um jogo! Nós queremos marcar pontos a cada vez que clicamos na bruxa mas também queremos ter um limite de tempo para a partida. Nós podemos usar uma variável para o score e para o cronometro.


1. Crie uma nova variávl para todos os sprites chamada score, e modifique o script da bruxa para incrementar esta variável de um quando ela é clicada.

```scratch

	when sprite1 clicked

	hide

	play sound Fairydust

	change score by 1
```
2. Vá para o Palco e crie uma nova variável (dessa vez somente para o palco) chamada cronometro. Adicione um novo script que é executado quando a bandeira verde é clicada para definir o cronometro para 30 e para reinicializar o score a 0. Então use um bloco 'repita até" para esperar um segundo e então diminue o cronometro de um. Isto deve repetir até que o timer seja 0, momento em que se deve usar stop all para interromper a partida.

```scratch

	when FLAG clicked

	set timer to 30

	set score to 0

	repeat until timer = 0

		wait 1 secs

		change timer by -1

	(end repeat)

	stop all
```

###Teste o seu projeto
__Clique na bandeira verde.__

Salve o seu projeto


###Coisas para tentar
__Como você faria para acelerar a bruxa durante o andamento da partida?__


__Parabéns, você terminou o jogo básicoe. Porém existem mais coisas que você pode fazer com o seu jogo. Tente este desafio!__

##Desafio: adicione mais bruxas

Se uma bruxa é bom, mais bruxas deve ser melhor! Vamos ter três bruxa voando pela tela.
1. Duplique a bruxa fazendo um clique direito nela na lista de sprites.
2. Para cada bruxa ajuste o tamanho do sprite para que as bruxas tenham tamanhos diferentes.
3. Para cada bruxa mude a variável velocidade para que eleas voem com velocidades diferentes.
4. Mova as bruxas pelo painel para que elas nao fiquem todas juntas.

###Teste o seu projeto
__Clique na bandeira verde.__

Você tem três bruxas que se movem de um lado a outro da tela, que aparecem e desaparecem aleatóriamente, e que desaparecem quando voce clica nelas?

Salve o seu projeto


###Coisas para tentar
1. Qual a quantidade adequada de bruxas para o jogo ?
2. Voce pode fazer as bruxas tenham aparências diferentes? Voce poderia editar suas fantasias, o usar alguns blocos da Looks palette para mudá-las.
3. Você pode fazer com o número de pontos ganhos por cada bruxa seja diferente ? Que tal fazer com que a bruxa mais veloz (e menor) valha 10 pontos?


__Parabéns voce terminou, agora aproveite o jogo !__
Não se esqueça que voce pode compartilhar seu jogo com todos os seus amigos e família clicando em __Compartilhar__ na barra de menu!
