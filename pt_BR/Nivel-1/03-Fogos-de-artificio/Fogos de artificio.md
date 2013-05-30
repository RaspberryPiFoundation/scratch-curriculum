Nível 1 

#Fogos de artifício.

__Introdução:__
Neste projeto, vamos criar um show de fogos de artifício sobre uma cidade.

##￼PASSO 1: Dispare um foguete na direção do mouse

__Vamos começar importando as imagens do jogo__

1. Crie um novo projeto Scratch. Exclua o gato clicando nele com o botão direito e em Excluir
2. Importe o fundo de tela outdoor/city-with-water
3. Use o botão __ Escolha um sprite do arquivo__ para adicionar um objeto Foguete
ao projeto (utilize Recursos/Foguete.png).
4. Faça o foguete desaparecer quando a bandeira verde for clicada.

Agora vamos fazer o foguete voar em direção ao mouse quando o mouse for clicado.

5. Adicione um bloco __quando tecla espaço pressionada__, faça o foguete aparecer e deslizar na direçao do mouse:

```scratch

    quando BANDEIRA clicada
    desapareça


    quando a tecla [espaço] for pressionada
    apareça
    deslize em (1) segundos para x: (mouse x) y: (mouse y) 
``` 

###Teste o projeto
__Clique na bandeira verde, posicione o mouse sobre o palco e pressione a barra de espaço.__

O foguete aparece e vai em direção ao mouse?
O que acontece se você mover o mouse e pressionar espaço novamente?

6. Fogos de artifício não andam de lado. Vamos fazer com que ele sempre comece na parte inferior da tela. Antes de fazer o foguete aparecer, use o bloco va para e faça com que ele va para a parte debaixo da tela, mas que mantenha a sua posiçao orizontal.

```scratch

    quando BANDEIRA clicada
    desapareça


    quando a tecla [espaço] for pressionada
    va para x: (mouse x) y: (-200)
    apareça
    deslize em (1) segundos para x: (mouse x) y: (mouse y)
```

###Teste o projeto
__Clique na bandeira verde, posicione o mouse sobre o palco e pressione a barra de espaço.__ 
O foguete voa em direçao ao mouse, saindo debaixo da tela? O que acontece se você mover o mouse e pressionar espaço novamente?

7. Finalmente, vamos usar o botão do mouse em vez da barra de espaço. Para fazer isso, nós podemos englobar nosso script com um __sempre se mouse pressionado__.
Em seguida, substituir o bloco __quando tecla espaço pressionada__ por __quando bandeira verde clicado__ e por último fazer com que o foguete esteja escondido no início.


```scratch

    quando BANDEIRA clicada
    desapareça 
    sempre se <mouse pressionado?>
      va para x: (mouse x) y: (-200)
      apareça
      deslize em (1) segundos para x: (mouse x) y: (mouse y) 
    fim
```
###Teste o projeto
__Clique na bandeira verde e em seguida, pressione o botão do mouse sobre o palco. Clique novamente em outro ponto.__ 

###Coisas para tentar
1. Tente alterar onde o foguete se posiciona antes de ser lançado, para que ele se incline um pouco enquanto se movimenta.
2. Tente fazer alguns foguetes mais lentos ou mais rápidos que os outros.

Salve o projeto.

## Passo 2: Faça o foguete explodir

￼ 1. O primeiro passo para fazer o foguete explodir é fazê-lo tocar o som Resources\bang antes que ele começa a se mover , em seguida, esconder-se, uma vez que chegar ao mouse. Para importar um som vá até a aba Sons e clique em importar.


```scratch

    quando BANDEIRA clicada
    desapareça
    sempre se <mouse pressionado?>
      va para x: (mouse x) y: (-200)
      toque o som [bang]
      apareça
      deslize em (1) segundos para x: (mouse x) y: (mouse y)
      desapareça
    fim
```
2. Em seguida, faça o foguete anuncie para todos uma nova mensagem quando ele explodir. Vamos ouvir essa mensagem mais tarde.transmitir.

```scratch

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
```
###Teste o projeto
__Clique na bandeira verde.__ 
Certifique-se de que o foguete faz barulho e se esconde quando atinge o mouse.

3. Importar um novo Sprite usando Resources/firework1.png
04. Quando ele recebe a mensagem de explodir, ele deve esconder-se e, em seguida, mover para a posição do foguete usando o bloco vá para, aparecer, em seguida, desaparecer novamente um segundo depois.

```scratch

    quando eu ouvir [explodir]
    desapareça
    va para x: ( [posição x ] do [foguete] ) y: ( [posição y ] do [foguete] )
    apareça
    espere (1) segundos
    desapareça
```
###Teste o projeto
__Lance um outro foguete.__ 
O foguete é substituído com o desenho de explosão quando ele explode?
O que acontece se você manter o botão pressionado enquanto move o mouse? (Não se preocupe, nós vamos corrigir isso mais tarde).

Salve seu projeto

## ￼PASSO 3: Faça com que cada explosão seja diferente

1. Agora nós podemos fazer com que cada explosão seja diferente, usando o bloco mude o efeito cor, e sorteando uma cor aleatória entre 1 e 200 antes de mostrá-lo.

```scratch

    quando eu ouvir [explodir]
    desapareça 
    mude o efeito [cor] para (sorteie número entre (1) e (200) ) 
    vá para x: ( [posição x ] do [foguete] ) y: ( [posição y ] do [foguete] ) 
    apareça 
    espere (1) segundos 
    desapareça

```

### Teste o projeto
__Clique na bandeira verde.____ 

Cada explosão tem uma cor diferente?

2. Vamos adicionar alguns desenhos diferentes para as explosões usando os trajes usando Resources/firework2.png e Resources/firework3.png, e alternar entre elas para cada foguete, antes de mostrá-lo.

###Testar seu projeto
__Clique na bandeira verde.____ 

Cada foguete tem um desenho de explosão diferente?

3. Finalmente, vamos fazer a explosão crescer ao longo do tempo ao invés de simplesmente aparecer. Em vez de esperar um segundo, defina o tamanho do sprite para 5% antes de mostrá-lo, e, em seguida, uma vez que é mostrado, duplique o tamanho do foguete cinqüenta vezes, usando um bloco de repetição.

```scratch

    quando eu ouvir [explodir]
    desapareça 
    mude o efeito [cor] para (sorteie número entre (1) e (200) ) 
    vá para x: ( [posição x ] do [foguete] ) y: ( [posição y ] do [foguete] ) 
    mude o tamanho para (5%) 
    apareça 
    repita (50) 
      mude o tamanho por (2) 
    fim 
    desapareça

```
###Teste o projeto
__Clique na bandeira verde.____ 

A a imagem da explosão se espalha a partir do centro e cresce lentamente?

### Coisas para tentar
Que tal tentar fazer cada explosão ainda mais original, alterando o tamanho e a velocidade de crescimento da explosão.

Salve seu projeto

## Passo 4: Correção do problema no anuncio da explosão 
Você lembra que tínhamos um problema quando mantínhamos pressionado o botão do mouse?
Isso ocorre porque quando o foguete anuncia sua explosão, ele vai repetir imediatamente e anunciar outra mensagem de explosão, antes que a última tenha terminado a exibição.


1. Para corrigir isso, podemos substituir o bloco anuncie, por um bloco anuncie e espere. Desta forma, o ciclo não se repetirá até que a foguete termine de explodir.

```scratch


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

```
### Teste o projeto
__Clique na bandeira verde e, em seguida, pressione o botão do mouse sobre o palco.__ 

A imagem da explosão aparece no lugar certo e na hora certa?

Salve seu projeto
