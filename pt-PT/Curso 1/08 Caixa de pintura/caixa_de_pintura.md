Nível 3

# Caixa de pintura

__Introdução:__ Vamos criar uma ferramenta de pintura para fazermos desenhos
sobre um quadro. Esta ferramenta permitirá escolher a cor do lápis, limpar o
quadro, usar carimbos e muito mais!

## PASSO 1: Arrastando e desenhando

Vamos começar com um lápis que risca quando é arrastado sobre a tela.

1. Cria um novo projecto no Scratch. Remove o actor gato clicando sobre ele, na
área dos actores, com o botão direito do rato e escolhendo «remover».

2. Clica sobre «o palco» e, em seguida, clica sobre o separador «Cenários» e
carrega um novo cenário a partir do arquivo «Recursos/quadro.png». Remove o
cenário antigo, todo branco.

3. Carrega um novo actor chamado «a ferramenta» a partir do arquivo
«Recursos/lápis verde.png».

4. Vai para o separador «Trajes» do novo actor. Confirma que o nome do único
traje existente é «lápis verde». Usa a ferramenta de especificação do centro do
traje, no canto superior direito do editor de pintura, para colocar esse centro
na ponta do lápis. Podes usar o _zoom_ para o fazeres com maior precisão.

5. Faz o actor ferramenta seguir o ponteiro do rato usando um bloco [repete para
sempre,] e um bloco [vai para a posição de [o ponteiro do rato ▼]], ambos sob o
bloco de início de guião quando a bandeira verde for clicada:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

__Vamos fazer com que o actor ferramenta se comporte como um lápis verdadeiro
(mais tarde poderá também comportar-se como borracha).__  Dá uma olhadela na
paleta «Caneta». Encontras nela vários blocos relacionados com a pintura. Por
enquanto os blocos que nos interessam são [baixa a tua caneta] e [levanta a tua
caneta].

6. Vamos usar o botão do rato para controlar a ferramenta – sempre que o botão
do rato estiver pressionado, o actor ferramenta __baixará a caneta__. Sempre que
o botão do rato não estiver pressionado, o actor ferramenta __levantará a
caneta__. Para isso, utiliza o comando [se &lt;>, então [] senão, []] e o
predicado &lt;o botão do rato está pressionado>:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
		se <o botão do rato está pressionado>, então
			baixa a tua caneta
		senão,
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ O actor ferramente, com a forma de um lápis, segue
o ponteiro do rato? O que acontece se mantiveres o botão do rato pressionado
enquanto o deslocas? Se o lápis não deixar um risco no palco quando o deslocas
mantendo o botão pressionado, experimenta aumentar o palco de modo a ocupar o
ecrã inteiro. Para isso, carrega no botão que se encontra sobre o canto superior
esquerdo do palco. O problema é que, quando estás no editor de projectos,
pressionar o botão do rato sobre um actor resulta no arrastamento desse actor,
que por isso nunca deixa traço, mesmo que a caneta esteja para baixo.

Não te preocupes com a cor com que desenhas, por enquanto.

__Para parar, carrega no sinal de _stop_.__

7. Com tantos testes, é inevitável que o quadro fique todo rabiscado. Podes usar
o comando [apaga tudo do palco] para apagar todos os rabiscos do quadro, que é
como quem diz, do palco.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
		se <o botão do rato está pressionado>, então
			baixa a tua caneta
		senão,
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ Os riscos desaparecem quando clicas na bandeira
verde?

__Para parar, carrega no sinal de _stop_.__

## PASSO 2: Apagando

Para não termos de reiniciar o projecto para apagar todos desenhos, vamos
adicionar um botão que apaga todo o quadro. Para fazer isso usamos também o
comando [apaga tudo do palco].

1. Carrega um novo actor a partir do arquivo "Recursos/o botão «cancelar»".

2. Confirma que o nome do novo actor é "o botão «cancelar»". Muda o nome do seu
único traje para «normal».

3. Posiciona o novo botão na parte de baixo do palco, sob o quadro, próximo do
lado esquerdo.

4. Cria o seguinte guião para este novo actor:

```scratch
	Quando alguém clicar em ti
	apaga tudo do palco
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ O botão de cancelar apaga todos os rabiscos do
quadro? O lápis surge à frente ou por trás do botão?

__Para parar, carrega no sinal de _stop_.__

5. Para garantires que o botão fica à frente do lápis, e que por isso
conseguimos clicar nele, usa o comando [vem para a frente] acrescentando um
outro guião ao novo actor:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	vem para a frente
	[fim do guião]
```

## PASSO 3: Mudando de cor

Até agora só desenhámos linhas azuis. Que tal usarmos cores diferentes?  Vamos
adicionar alguns botões coloridos por baixo do quadro, junto ao botão de
cancelar.  Quando clicares num desses botões, a cor do lápis mudará para a cor
do botão. O actor instrumento também mudará o seu traje para um lápis da mesma
cor para podermos saber com que cor estamos a desenhar.

1. Carrega um novo actor a partir do arquivo «Recursos/o botão vermelho.gif».
Altera o nome do seu único traje para «normal».

2. Posiciona o novo actor na base do palco, sob o quadro, ao lado do botão de
cancelar.

3. Quando o botão vermelho for clicado, ele deve difundir a mensagem «Eu, botão
vermelho, fui clicado!». Além disso, deve surgir à frente do lápis, para que o
possamos clicar. Cria os seguintes guiões para o novo actor:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	vem para a frente
	[fim do guião]

	Quando alguém clicar em ti
	difunde a mensagem [«Eu, botão vermelho, fui clicado!» ▼]
	[fim do guião]
```

__Isso mesmo: são apenas dois blocos em cada guião! A parte complicada fica a
cargo da ferramenta.__

No actor ferramenta, carrega um novo traje a partir do arquivo «Recursos/lápis
vermelho.png». Confirma que o seu nome é «lápis vermelho». Tal como fizeste para
o traje original, usa a ferramenta de especificação do centro do traje, no canto
superior direito do editor de pintura, para colocar esse centro na ponta do
lápis. Podes usar o _zoom_ para o fazeres com maior precisão.

4. Adiciona um novo guião à ferramenta. Quando a ferramenta receber a mensagem
«Eu, botão vermelho, fui clicado!», deve mudar para o traje «lápis vermelho» e
alterar a cor da sua caneta para vermelho, usando o comando [altera a cor da tua
caneta para []].

__Dica:__ No comando [altera a cor da tua caneta para []] existe um quadradinho
colorido no qual podes clicar para, usando uma pipeta, clicares sobre o botão
vermelho, «sugando» a sua cor, de modo a garantir que a caneta da ferramenta e o
botão tenham exactamente a mesma cor.

```scratch
	Quando receberes a mensagem [«Eu, botão vermelho, fui clicado!» ▼]
	muda o traje para [lápis vermelho ▼]
	altera a cor da tua caneta para [#f00]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ Desenha uma linha. Depois, clica sobre o botão
vermelho, para seleccionar a cor vermelha. Desenha de novo. A ferramenta muda
para o lápis vermelho? Passa a desenhar a vermelho? Os riscos são feitos pela
ponta do lápis?

__Para parar, carrega no sinal de _stop_.__

5. Repete o que acabaste de fazer, mas agora usando os botões azul, amarelo e
verde e os respectivos trajes para o lápis (reordena-os de modo a que o traje do
lápis verde seja o último, para ficares com as cores pela mesma ordem em todo o
lado).

### Testa o teu projecto

__Clica na bandeira verde.__ Todos os botões de cor funcionam? Todos levam à
mudança do traje da ferramenta para o lápis da cor certa?  Todos fazem o lápis
desenhas na cor certa? O desenho é sempre feito pela ponta do lápis?

__Para parar, carrega no sinal de _stop_.__

## PASSO 4: Desenhando apenas dentro do quadro

Já deves ter notado que podes desenhar em qualquer lugar do palco, mesmo que
seja fora do quadro de desenho.  Não queremos que isso aconteça. Queremos que os
desenhos se realizem apenas sobre o quadro. Temos, por isso, de restringir a
posição da ferramenta à área de desenho - a parte em cinzento menos escuro do
palco, acima da zona reservada para os botões.

Lembra-te que o Scratch define a localização de pontos no palco usando
coordenadas x e y.  A área de desenho encontra-se entre as coordenadas -229 e
229 no eixo x e as coordenadas -119 e 168 no eixo y, em ambos os casos
_inclusive_. Podemos indicar as coordenadas válidas usando desigualdades. Para o
eixo x, as coordenadas válidas no eixo x são aquelas para as quais -229 ≤ x e x
≤ 229 ou, o que é o mesmo, visto que as coordenadas dos píxeis no Scratch tomam
apenas valores inteiros, -230 < x e x < 230. Da mesma forma, as coordenadas
válidas no eixo y são aquelas para as quais -119 ≤ y e y ≤ 168 ou, o que é o
mesmo, pelas razões que vimos atrás, -120 < y e y < 169.

Podemos usar estes valores na condição de um comando [se &lt;>, então []], de
modo a garantir que só movemos a ferramenta se o ponteiro do rato estiver dentro
da área pretendida. Põe um comando condicional [se &lt;>, então []] em torno do
comando [vai para a posição de [o ponteiro do rato ▼]] já existente e, como
condição do comando condicional, usa &lt;&lt;&lt;[-230] &lt; (a coordenada x do
rato)> e &lt;(a coordenada x do rato) &lt; [230]>> e &lt;&lt;[-120] &lt; (a
coordenada y do rato)> e &lt;(a coordenada y do rato) &lt; [169]>>>.

__Nota:__ Precisas de usar três predicados &lt;&lt;> e &lt;>>, um para verificar
a coordenada x, outro para a coordenada y, e ainda outro para juntar as duas
verificações, bem como quatro predicados &lt;[] &lt; []> para verificar os
valores extremos em x e em y.

Altera o guião principal da ferramenta de modo a ficar como se segue:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		se <<<[-230] < (a coordenada x do rato)> e <(a coordenada x do rato) < [230]>> e <<[-120] < (a coordenada y do rato)> e <(a coordenada y do rato) < [169]>>>, então
			[vai para a posição de [o ponteiro do rato ▼]]
		[fim do comando «se então»]
		se <o botão do rato está pressionado>, então
			baixa a tua caneta
		senão,
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

Como não é possível desenhar fora da área de desenho, podemos esconder a
ferramenta sempre que o ponteiro do rato estiver fora dessa área. Para o fazer,
substitui o comando [se &lt;>, então []] por um comando [se &lt;>, então []
senão, []]. Mantém a mesma condição que antes e faz com que a ferramenta se
mostre quando a condição for verdadeira e se esconda quando ela for falsa.
Aproveita para levantar a caneta quando o ponteiro do rato ficar fora da área de
desenho e para passar para debaixo do comando [mostra-te] os blocos já
existentes de controlo da caneta segundo o estado do botão do rato:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		se <<<[-230] < (a coordenada x do rato)> e <(a coordenada x do rato) < [230]>> e <<[-120] < (a coordenada y do rato)> e <(a coordenada y do rato) < [169]>>>, então
			[vai para a posição de [o ponteiro do rato ▼]]
			mostra-te
			se <o botão do rato está pressionado>, então
				baixa a tua caneta
			senão,
				levanta a tua caneta
			[fim do comando «se então senão»]
		senão
			esconde-te
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ Consegues desenhar dentro do quadro, i.e., dentro
da área de desenho? Consegues desenhar fora dessa área? O que acontece com a
ferramenta quando o ponteiro sai da área de desenho e volta a entrar noutro
local? Consegues desenhar junto das bordas superior e direita do quadro? Porquê?

__Para parar, carrega no sinal de _stop_.__

## DESAFIO 1: Faz a ferramenta chegar a todas as bordas e cantos do quadro

Neste momento a ferramenta não atinge duas regiões do quadro: a que está junto à
borda superior do quadro e a que está junto à borda direita do quadro. Isso
acontece

- porque os nossos trajes em forma de lápis têm a «cauda» para cima e para a
direita (isto quando a orientação da ferramenta é a «normal», ou seja, para a
direita, ou seja ainda, 90°) e

- porque o Scratch não deixa que os actores saiam demasiado da zona visível do
palco. 

A solução para este problema passa por alterar a orientação da ferramente sempre
que este se aproximar de pelo menos uma das bordas.

Por exemplo:

- Perto da borda esquerda: abaixo do meio, dar a orientação normal, i.e., 90°,
acima do meio, dar a orientação 180°.

- Perto da borda direita: abaixo do meio, dar a orientação 0°, acima do
meio, dar a orientação -90°.

- Perto da borda inferior: à esquerda do meio, dar a orientação normal, i.e.,
90°, à direita do meio, dar a orientação 0°.

- Perto da borda superior: à esquerda do meio, dar a orientação normal, i.e.,
180°, à direita do meio, dar a orientação -90°.

Podes, por exemplo, considerar que por «perto» de uma borda do quadro se entende
estar a menos de 40 passos ou píxeis de distância dessa borda.

## PASSO 5: Apagando com uma borracha

__Desenhar linhas é bestial, mas por vezes também é preciso apagar o que se
escreveu para corrigir erros.__ Podemos vamos fazer isso criando um novo modo
para ferramenta que desenha a cinzento, ou seja, na mesma cor que o fundo.

1. Adiciona um novo actor que servirá para o utilizador poder selecionar a
borracha. Adiciona-o a partir do arquivo «Recursos/borracha.png». Altera o nome
desse actor para "o botão «borracha»".

2. Altera o nome do seu único traje para «normal». Diminui a dimensão desse
traje, no editor de pintura, de modo a que caiba na faixa sob o quadro.

3. Desloca o novo botão para a faixa sob o quadro, colocando-o ao lado dos
botões de selecção da cor.

Este actor deve funcionar exactamente da mesma forma que os botões de selecção
de cor. Isto é, deve vir para a frente no início da execução do projecto e deve
difundir uma mensagem apropriada quando for clicado.

4. Copia para o actor botão «borracha» os guiões de algum dos outros botões de
selecção de cor. Altera a mensagem a difundir para "Eu, botão «borracha», fui
clicado!".

A ferramenta deve ficar à escuta da mensagem "Eu, botão «borracha», fui
clicado!" e, quando a receber, deve mudar a cor da caneta para a cor cinzenta do
quadro. Lembra-te que podes usar a __pipeta__ para «sugar» a cor do quadro.
Também precisas de um novo traje para representar a borracha: usa o mesmo
arquivo que usaste para o botão: «Recursos/borracha.png».

__Lembra-te de redefinir a posição do centro do traje!__ Coloca-o na ponta da
borracha que parece assentar na superfície quadro.

### Testa o teu projecto

__Clica na bandeira verde.__ Clica sobre o botão «borracha». A ferramenta muda
para o aspecto de uma borracha e apaga os desenhos? É eficaz? Funciona até às
bordas do quadro? Consegues alternar entre a borracha e os lápiz das outras
cores?

__Para parar, carrega no sinal de _stop_.__

## DESAFIO 2: Aumenta a espessura da borracha

De modo a tornar a utilização da borracha mais eficiente, experimenta aumentar a
espessura da caneta quando a borracha for seleccionada. Não te esqueças de repor
a espessura se o utilizador voltar a seleccionar uma das quatro cores!

## PASSO 6: Carimbando

A próxima coisa a acrescentar é uma ferramenta de carimbo, para carimbar
pequenas imagens no quadro.

Actividades a realizar:

1. Adiciona um novo actor, usando a imagem ou o traje que preferires. Chama a
esse actor "o botão «carimbo»". Se o actor tiver vários trajes, remove todos
menos o traje que mais te agradar. Dá o nome «normal» a esse traje.

2. Reduz esse traje de modo a que o botão caiba na faixa sob o quadro, ao lado
dos outros botões. Desloca-o para lá.

3. Copia para este novo botão os guiões do botão «borracha».

4. Quando este novo botão for clicado, deve difundir a mensagem "Eu, botão
«carimbo», fui clicado!".

5. Adicione um novo traje à ferramenta. Adiciona o mesmo traje que escolheste
para o botão «carimbo». Chama a esse traje «carimbo». Ajusta a dimensão desse
traje para que as carimbadelas não fiquem demasiado grandes nem demasiado
pequenas. Assegura-te que o centro do traje está bem centrado na imagem.

6. Adiciona um novo guião à ferramenta para ficar à escuta da mensagem "Eu,
botão «carimbo», fui clicado!". Tal como antes, esse novo guião deve mudar para
o novo traje assim que receber essa mensagem.

7. Finalmente, altera o guião principal da ferramenta de modo a que, quando o
botão do rato estiver pressionado, a ferramenta se carimbe no palco se o traje
corrente for «carimbo» (usa o número desse traje, que provavelmente é o 6, para
o distinguir dos demais trajes) e baixe a caneta quando o traje corrente for
outro qualquer.

### Testa o teu projecto

__Clica na bandeira verde.__ Clica no botão «carimbo». Faz umas quantas
carimbadelas. O carimbo funciona corretamente? O que acontece quando clicas nos
botões de selecção da cor do lápis?

__Para parar, carrega no sinal de _stop_.__

__Parabéns! Completaste os passos básicos deste projecto e, esperamos, aceitaste
também e completaste os dois primeiros desafios! Aceita agora os desafios
adicionais!__

## DESAFIO 3: Adiciona um lápis arco-íris

Adiciona um lápis especial que pinta nas cores do arco-íris. O que vais fazer
não é possível usando canetas ou lápis comuns, e por isso é uma boa demonstração
de que usar um computador permite  fazer coisas diferentes. O segredo é usar o
comando [adiciona () à cor da tua caneta].

Começa por adicionar ao projecto um novo actor «o botão arco-íris» e ao actor «a
ferramenta» um novo traje «lápis arco-íris»:

1. Cria um novo actor a partir do arquivo «Recursos/o botão arco-íris». Coloca-o
ao lado dos outros botões de selecção da cor do lápis. Copia para o novo actor
os guiões de qualquer dos outros botões de selecção da cor do lápis, alterando
para «Eu, botão arco-íris, fui clicado!» a mensagem difundida quando o actor for
clicado.

2. Adiciona à ferramenta um novo traje a partir do arquivo «Recursos/lápis arco-
íris». Faz como fizeste no caso dos outros trajes representando lápis para
acertar a localização do centro deste traje.

3. Adiciona um guião à ferramenta que fica à escuta da mensagem «Eu, botão arco-
íris, fui clicado!» e, quando a recebe, altera o traje para o «lápis arco-íris».

4. Adiciona um guião para garantir que a cor da caneta se vai alterando com o
tempo quando o traje da ferramenta é «lápis arco-íris» (adicionar 5 à cor e 3 ao
tom de 0,05 em 0,05 segundos resulta bem, mas podes experimentar outros
valores). Podes resolver o problema da seguinte forma (admitimos que o traje
«lápis arco-íris» tem o número 5):

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		espera até que <(o número do traje) = [5]>
		adiciona (5) à cor da tua caneta
		espera (0.05) s
	[fim do comando «repete para sempre»]
	[fim do guião]
```

Há outras formas de resolver o problema, claro. Consegues encontrá-las? Que
vantagens ou desvantagens têm?

### Testa o teu projecto

__Clica na bandeira verde.__ Clica no botão arco-íris. O lápis arco-íris
funciona correctamente? O que acontece se voltares a usar um dos lápis normais?

__Para parar, carrega no sinal de _stop_.__

## DESAFIO 4: Cria atalhos do teclado

Para além de se poderem usar os botões sob o quadro para realizar acções, tais
como escolher o tipo de ferramenta de desenho a usar, queremos que seja também
possível usar teclas de atalho. Para isso podemos recorrer a um bloco [Quando
alguém pressionar a tecla [... ▼]] por cada tecla. O efeito deve ser exactamente
o mesmo que clicar no botão correspondente, pelo que os guiões serão quase
iguais. Cria um guião adicional por botão para activar os atalhos do teclado
correspondentes:

* Apagar o quadro - tecla «a»
* Lápis vermelho (encarnado) - tecla «e»
* Lápis azul - tecla «z»
* Lápis amarelo - tecla «m»
* Lápis verde - tecla «v»
* Lápis arco-íris - tecla «i»
* Borracha - tecla «b»
* Carimbo - tecla «c»

### Testa o teu projecto

__Clica na bandeira verde.__ Todos os atalhos de teclado funcionam? O resultado
de usar um atalho é o mesmo que o de usar o botão correspondente?

__Para parar, carrega no sinal de _stop_.__

## DESAFIO 5: Adiciona suporte para aumentar e diminuir a espessura do lápis ou da borracha, ou o tamanho do carimbo

Na maioria dos pacotes de desenho pode-se alterar a espessura do lápis ou da
borracha. Vamos adicionar essa possibilidade, bem como a possibilidade de
alterar a dimensão do carimbo.

Há uma complicação nisto: para o lápis e para a borracha, a alteração afecta a
espessura da caneta, enquanto no caso do carimbo a alteração afecta a dimensão
do carimbo, ou seja, alterar a dimensão do actor. Tudo depende do que se estiver
a usar na altura. Pior, alterar a dimensão do actor durante a utilização do
carimbo não deve levar à alteração da dimensão do actor quando a ferramenta
usada é outra.

Cria dois novos actores, "o botão «aumentar»" e "o botão «reduzir»", a partir
dos arquivos "Recursos/o botão «aumentar».gif" e "Recursos/o botão
«reduzir».gif", respectivamente. Estes botões devem recorrer à difusão de
mensagens, tal como os restantes botões (com excepção do botão de apagar o
quadro).

A ferramenta pode ficar à escuta destas mensagens, alterando em 10 o tamanho do
actor ou em 1 a espessura da caneta, dependendo do traje corrente ser ou não, o
carimbo.

Não te esqueças dos atalhos do teclado para os novos botões. Podes usar, por
exemplo, as setas para cima e para baixo.

Não te esqueças de fazer o tamanho regressar a 100% sempre que o traje mudar
para algo que não o «carimbo». Se não o fizeres, alterar o tamanho do carimbo
levará a que, quando mudares para o lápis ou para a borracha, estes também terão
alterado de tamanho.

Finalmente, arranja forma de o tamanho do carimbo ser recordado, para que quando
voltares ao carimbo, depois de passares pelo lápis ou pela borracha, o tamanho
anterior não tenha sido esquecido. A maneira mais fácil de o conseguires é
criares uma nova variável para guardar o tamanho do actor à medida que este é
alterado e para repor o tamanho do actor ao regressares ao carimbo depois de
passares pelo lápis ou pela borracha.

### Testa o teu projecto

__Clica na bandeira verde.__ O controlo da espessura do lápis funciona? E o
controlo do tamanho do carimbo? O que acontece alterares o tamanho do carimbo,
passares para o lápis ou para a borracha e, em seguida, voltares ao carimbo? O
seu tamanho mantém-se?

__Para parar, carrega no sinal de _stop_.__

__Parabéns! Terminaste! Agora podes desfrutar do jogo!__

Não te esqueças de que podes partilhar o teu jogo com os outros Scratchadores,
incluindo os teus amigos e os teus familiares, clicando em «Partilhar»!ß
