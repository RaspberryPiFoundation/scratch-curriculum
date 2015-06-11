---
title: Fogos de artifício
term: 1
resources: 1
---

Nível 1

#Fogos de artifício

__Introdução:__
Neste projeto, vamos criar um show de fogos de artifício em uma cidade.

##PASSO 1: Dispare um foguete na direção do mouse

__Vamos começar importando as imagens do jogo.__

1. Crie um novo projeto Scratch. Apague o gato clicando nele com o botão direito e em apagar.
2. Importe o fundo de tela outdoor/city-with-water.
3. Use o botão _Escolha um sprite do arquivo_ para adicionar um objeto Foguete ao projeto (utilize Recursos/foguete.png).
4. Faça o foguete desaparecer quando a bandeira verde for clicada.
5. Também vamos fazer o foguete voar em direção ao mouse quando a tecla espaço for pressionada.
Adicione um comando __quando tecla espaço pressionada__, faça o foguete aparecer e deslizar na direção do mouse:


	    quando BANDEIRA clicado
	    desapareça

	    quando a tecla [espaço] for pressionada
	    apareça
	    deslize em (1) segundos para x: (mouse x) y: (mouse y)

###Teste o projeto
__Clique na bandeira verde, posicione o mouse sobre o palco e pressione a barra de espaço.__

O foguete aparece e vai em direção ao mouse?
O que acontece se você mover o mouse e pressionar espaço novamente?

6. Fogos de artifício não andam de lado. Vamos fazer com que ele sempre comece embaixo da tela alinhado com o mouse.
Antes de fazer o foguete aparecer, use o comando __vá para__ e faça com que ele vá para a parte de baixo da tela, m
as que mantenha a sua posição horizontal (x) do mouse.



	    quando BANDEIRA clicado
	    desapareça


	    quando a tecla [espaço] for pressionada
	    vá para x: (mouse x) y: (-200)
	    apareça
	    deslize em (1) segundos para x: (mouse x) y: (mouse y)


###Teste o projeto
__Clique na bandeira verde, posicione o mouse sobre o palco e pressione a barra de espaço.__

O foguete voa na direção do mouse, saindo debaixo da tela?

O que acontece se você mover o mouse e pressionar espaço novamente?

7. Por último, vamos usar o botão do mouse em vez da barra de espaço. Para fazer isso,
nós podemos colocar nossos comandos dentro de um bloco __sempre se mouse pressionado__.
Em seguida, substituir o comando __quando tecla espaço pressionada__ por __quando bandeira verde clicado__
e por último fazer com que o foguete não esteja aparecendo no início.




	    quando BANDEIRA clicado
	    desapareça
	    sempre se <mouse pressionado?>
	      vá para x: (mouse x) y: (-200)
	      apareça
	      deslize em (1) segundos para x: (mouse x) y: (mouse y)
	    fim

###Teste o projeto
__Clique na bandeira verde e em seguida, clique sobre o palco. Clique novamente em outro ponto.__

###Sugestões
1. Tente alterar onde o foguete se posiciona antes de ser lançado, para que ele se incline um pouco enquanto se movimenta.
2. Tente fazer alguns foguetes mais lentos ou mais rápidos que os outros.

Salve o projeto.

## Passo 2: Faça o foguete explodir

1. O primeiro passo para fazer o foguete explodir é fazê-lo tocar o som Recursos\bang antes que ele comece a se mover, em seguida, desaparecer,
 uma vez que chegar ao mouse. Para importar um som vá até a aba Sons e clique em importar.

		quando BANDEIRA clicado
		desapareça
		sempre se <mouse pressionado?>
		    va para x: (mouse x) y: (-200)
		    toque o som [bang]
		    apareça
		    deslize em (1) segundos para x: (mouse x) y: (mouse y)
		    desapareça
		fim

2. Em seguida, faça o foguete anunciar para todos uma nova mensagem quando ele explodir. Esta mensagem será ouvida mais tarde.



	    quando BANDEIRA clicado
	    desapareça
	    sempre se <mouse pressionado?>
	      va para x: (mouse x) y: (-200)
	      toque o som [bang]
	      apareça
	      deslize em (1) segundos para x: (mouse x) y: (mouse y)
	      desapareça
	      anuncie [explodir] para todos
	    fim

###Teste o projeto
__Clique na bandeira verde.__
Certifique-se de que o foguete faz barulho e desaparece quando atinge o mouse.

3. Importe um novo objeto usando Recursos/explosao.png.
4. Quando ele ouve a mensagem explodir, ele deve desaparecer e, em seguida, mover para a posição do foguete usando o comando __vá para__.
 A explosão deve aparecer, em seguida, desaparecer novamente um segundo depois.



	    quando eu ouvir [explodir]
	    desapareça
	    va para x: ( [posição x v] de [foguete v] ) y: ( [posição y v] de [foguete v] )
	    apareça
	    espere (1) segundos
	    desapareça

###Teste o projeto

__Lance um outro foguete.__

O foguete é substituído pelo desenho de explosão quando ele explode?
O que acontece se você mantiver o botão pressionado enquanto move o mouse? (Não se preocupe, nós vamos corrigir isso mais tarde).

Salve o projeto

##PASSO 3: Faça com que cada explosão seja diferente

1. Nós podemos fazer com que cada explosão seja diferente, usando o comando __mude o efeito cor__,
e sorteando uma cor aleatória entre 1 e 200 antes de mostrá-lo.

	    quando eu ouvir [explodir]
	    desapareça
	    mude o efeito [cor] para (sorteie número entre (1) e (200) )
	    vá para x: ( [posição x v] de [foguete v] ) y: ( [posição y v] de [foguete v] )
	    apareça
	    espere (1) segundos
	    desapareça


### Teste o projeto
__Clique na bandeira verde.__

Cada explosão tem uma cor diferente?

2. Vamos inserir alguns desenhos diferentes para as explosões usando os trajes  Recursos/explosao2.png e Recursos/explosao3.png,
e alternar entre elas para cada foguete, antes de mostrá-lo.

###Teste o projeto
__Clique na bandeira verde.__

Cada foguete tem um desenho de explosão diferente?

3. Finalmente, vamos fazer a explosão crescer ao longo do tempo ao invés de simplesmente aparecer.
No lugar de esperar um segundo, defina o tamanho do objeto para 5% antes de mostrá-lo, e, em seguida, uma vez que é mostrado,
some 2 ao tamanho cinqüenta vezes, usando um bloco de repetição.


	    quando eu ouvir [explodir]
	    desapareça
	    mude o efeito [cor] para (sorteie número entre (1) e (200) )
	    vá para x: ( [posição x v] de [foguete v] ) y: ( [posição y v] de [foguete v] )
	    mude o tamanho para (5%)
	    apareça
	    repita (50)
	      mude o tamanho por (2)
	    fim
	    desapareça

###Teste o projeto
__Clique na bandeira verde.__

A imagem da explosão se espalha a partir do centro e cresce lentamente?

### Sugestões
Que tal tentar fazer cada explosão ainda mais original, alterando o tamanho e a velocidade de crescimento da explosão.

Salve o projeto

## PASSO 4: Correção do problema no anuncio da explosão
Você lembra que tínhamos um problema quando mantínhamos pressionado o botão do mouse?
Isso ocorre porque quando o foguete anuncia sua explosão, ele vai repetir imediatamente e anunciar outra mensagem de explosão,
antes que a última tenha terminado a exibição.


1. Para corrigir isso, podemos substituir o comando anuncie, por um comando anuncie e espere.
Desta forma, o ciclo não se repetirá até que a foguete termine de explodir.




	    quando BANDEIRA clicado
	    desapareça
	    sempre se <mouse pressionado?>
	    vá para x: (mouse x) y: (-200)
	    toque o som [bang]
		apareça
		deslize em (1) segundos para x: (mouse x) y: (mouse y)
		desapareça
		anuncie [explodir] para todos e espere
	    fim


### Teste o projeto
__Clique na bandeira verde e em seguida, pressione o botão do mouse sobre o palco.__

A imagem da explosão aparece no lugar certo e na hora certa?

Salve o projeto
