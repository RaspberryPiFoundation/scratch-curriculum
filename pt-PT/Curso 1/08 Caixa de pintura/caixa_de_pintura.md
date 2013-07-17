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

3. Carrega um novo actor chamado «o lápis» a partir do arquivo «Recursos/o lápis
verde.png».

4. Vai para o separador «Trajes» do novo actor. Muda o nome do único traje
existente para «verde». Usa a ferramenta de especificação do centro do traje, no
canto superior direito do editor de pintura, para o colocar na ponta da caneta.
Podes usar o _zoom_ para o fazeres com maior precisão.

5. Faz a caneta seguir o ponteiro do rato usando um bloco [repete para sempre,]
e um bloco [vai para a posição de [o ponteiro do rato ▼]], ambos sob o bloco de
início de guião quando a bandeira verde for clicada:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

__Vamos fazer com que o actor lápis se comporte como um lápis verdadeiro.__  Dá
uma olhadela na paleta «Caneta». Encontras nela vários blocos relacionados com a
pintura. Por enquanto os blocos que nos interessam são [baixa a tua caneta] e
[levanta a tua caneta].

6. Vamos usar o botão do rato para controlar o lápis – sempre que o botão do
rato estiver pressionado, o actor lápis __baixará a caneta__. Sempre que o botão
do rato não estiver pressionado, o actor lápiz __levantará a caneta__.  Para
isso, utiliza o comando [se &lt;>, então senão,] e o predicado &lt;o botão do
rato está pressionado>:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
		se &lt;o botão do rato está pressionado>, então
			baixa a tua caneta
		senão,
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ O lápis segue o ponteiro do rato? O que acontece se
mantiver o botão do rato pressionado enquanto o desloca? Se o lápis não deixar
um risco no palco quando o desloca mantendo o botão pressionado, experimenta
aumentar o palco de modo a ocupar o ecrã inteiro. Para isso, carrega no botão
que se encontra sobre o canto superior esquerdo do palco. O problema é que,
quando estás no editor de projectos, pressionar o botão do rato sobre um actor
resulta no arrastamento desse actor, que nunca deixa traço, mesmo que a caneta
esteja para baixo.

Não te preocupes com a cor do lápis, por enquanto.

__Para parar, carrega no sinal de _stop_.__

7. Com tantos testes, é inevitável que o quadro fique todo rabiscado. Podes usar
o comando [apaga tudo do palco] para apagar todos os rabiscos do quadro, que é
como quem diz, do palco.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		[vai para a posição de [o ponteiro do rato ▼]]
		se &lt;o botão do rato está pressionado>, então
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

1. Carrega um novo actor a partir do arquivo «Recursos/o botão «cancelar».

2. Confirma que o nome do novo actor é "o botão «cancelar»". Muda o nome do seu único traje para «normal».

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
do botão. O actor lápis também mudará de cor para podermos saber com que cor
estamos a desenhar.

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
cargo do lápis.__

No actor lápis, carrega um novo traje a partir do arquivo «Recursos/o lápis
vermelho.png». Altera o seu nome para «vermelho». Tal como fizeste para o traje
original, usa a ferramenta de especificação do centro do traje, no canto
superior direito do editor de pintura, para o colocar na ponta da caneta. Podes
usar o _zoom_ para o fazeres com maior precisão.

4. Adiciona um novo guião ao lápis. Quando o lápis receber a mensagem «Eu, botão
vermelho, fui clicado!», deve mudar para o traje «vermelho» e alterar a cor da
sua caneta para vermelho, usando o comando [altera a cor da tua caneta para []].

__Dica:__ No comando [altera a cor da tua caneta para []] existe um quadradinho
colorido, no qual podes clicar para,  usando a pipeta, clicar sobre o botão
vermelho, «sugando» a sua cor, de modo a garantir que a caneta do lápis e o
botão tenham exactamente a mesma cor.

```scratch
	Quando receberes a mensagem [«Eu, botão vermelho, fui clicado!» ▼]
	muda o traje para [vermelho ▼]
	altera a cor da tua caneta para [#f00]
	[fim do guião]
```

### Testa o teu projecto

__Clica na bandeira verde.__ Desenha uma linha. Depois, clica sobre o botão
vermelho, para seleccionar a cor vermelha. Desenha de novo. O O lápis muda para
o traje vermelho? Passa a desenhar a vermelho? Os riscos são feitos pela ponta
do lápis?

__Para parar, carrega no sinal de _stop_.__

5. Repete o que acabaste de fazer, mas agora usando os botões azul, amarelo e
verde e os respectivos trajes para o lápis (reordena-os de modo a que o traje
verde seja o último, para ficares com as cores pela mesma ordem em todo o lado).

##Testa o teu projecto

__Clica na bandeira verde.__ Todos os botões de cor funcionam? Todos levam à
mudança do traje do lápis para a cor certa?  Todos fazem o lápis escrever na cor
certa? O desenho é sempre feito pela ponta do lápis?

__Para parar, carrega no sinal de _stop_.__

## PASSO 4: Desenhando apenas dentro do quadro

Já deves ter notado que podes desenhar em qualquer lugar do palco, mesmo que
seja fora do quadro  de desenho.  Não queremos que isso aconteça. Queremos que
os desenhos se realizem apenas sobre o quadro. Temos por isso de restringir a
posição do lápis à área de desenho - a parte em cinzento menos escuro do palco,
acima da zona reservada para os botões.

Lembra-te que o Scratch define a localização de pontos no palco usando
coordenadas x e y.  A área de desenho encontra-se entre as coordenadas -229 e
229 no eixo x e as coordenadas -119 e 168 no eixo y, em ambos os casos
inclusive. Podemos indicar as coordenadas válidas usando desigualdades. Para o
eixo x, as coordenadas válidas no eixo x são aquelas para as quais -229 ≤ x e x
≤ 229 ou, o que é o mesmo, visto que as coordenadas dos píxeis no Scratch tomam
apenas valores inteiros, -230 < x e x < 230. Da mesma forma, as coordenadas
válidas no eixo y são aquelas para as quais -119 ≤ y e y ≤ 168 ou, o que é o
mesmo, pelas razões que vimos atrás, -120 < y e y < 169.

Podemos usar estes valores na condição de um comando [se &lt;>, então], de modo
a garantir que só deslocamos o rato se o ponteiro do rato estiver dentro da área
pretendida. Põe um comando condicional [se &lt;>, então] em torno do comando
[vai para a posição de [o ponteiro do rato ▼]] já existente e, como condição do
comando condicional, usa &lt;&lt;&lt;[-230] &lt; (a coordenada x do rato)> e
&lt;(a coordenada x do rato) &lt; [230]>> e &lt;&lt;[-120] &lt; (a coordenada y
do rato)> e &lt;(a coordenada y do rato) &lt; [169]>>>.

__Nota:__ Precisas de usar três predicados &lt;&lt;> e &lt;>>, um para verificar a coordenada x, outro para a coordenada y, e ainda outro para juntar as duas verificações, bem como quatro predicados &lt;[] &lt; []> para verificar os valores extremos em x e em y.

Altera o guião principal do actor lápis de modo a ficar como se segue:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		se &lt;&lt;&lt;[-230] &lt; (a coordenada x do rato)> e &lt;(a coordenada x do rato) &lt; [230]>> e &lt;&lt;[-120] &lt; (a coordenada y do rato)> e &lt;(a coordenada y do rato) &lt; [169]>>>, então
			[vai para a posição de [o ponteiro do rato ▼]]
		[fim do comando «se então»]
		se &lt;o botão do rato está pressionado>, então
			baixa a tua caneta
		senão,
			levanta a tua caneta
		[fim do comando «se então senão»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

Como não é possível desenhar fora da área de desenho, podemos esconder o lápis
sempre que ele estiver fora dessa área. Para o fazer, substitui o comando [se
&lt;>, então] por um comando [se &lt;>, então senão,]. Mantem a mesma condição
que antes e faz com que o lápis se mostre quando a condição for verdadeira e se
esconda quando ela for falsa. Aproveita para levantar a caneta quando o ponteiro
do rato ficar fora da área de desenho e para passar para baixo do comando
[mostra-te] os blocos já existentes de controlo da caneta segundo o estado do
botão do rato:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	apaga tudo do palco
	repete para sempre,
		se &lt;&lt;&lt;[-230] &lt; (a coordenada x do rato)> e &lt;(a coordenada x do rato) &lt; [230]>> e &lt;&lt;[-120] &lt; (a coordenada y do rato)> e &lt;(a coordenada y do rato) &lt; [169]>>>, então
			[vai para a posição de [o ponteiro do rato ▼]]
			mostra-te
			se &lt;o botão do rato está pressionado>, então
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
da área de desenho? Consegues desenhar fora dessa área? O que acontece com o
lápis quando o ponteiro sai da área de desenho e volta a entrar noutro local? Consegues desenhar junto das bordas superior e direita do quadro? Porquê?

## DESAFIO 1: Faz o lápis chegar a todas as bordas e cantos do quadro

Neste momento o lápis não atinge duas regiões do quadro: a que está junto à
borda superior do quadro e a que está junto à borda direita do quadro. Isso
acontece porque o nosso lápiz tem a «cauda» orienta para cima e para a direita
e porque o Scratch não deixa os actores sairem demasiado da zona visível do
palco. A solução para este problema passa por alterar a orientação do lápis
sempre que este se aproximar de uma das bordas, como se segue:

- Perto da borda esquerda: abaixo do meio, dar a orientação normal, i.e., 90°,
acima do meio, dar a orientação 180°.

- Perto da borda direita: abaixo do meio, dar a orientação 0°, acima do
meio, dar a orientação -90°.

- Perto da borda inferior: à esquerda do meio, dar a orientação normal, i.e.,
90°, à direita do meio, dar a orientação 0°.

- Perto da borda superior: à esquerda do meio, dar a orientação normal, i.e.,
180°, à direita do meio, dar a orientação -90°.

Podes, por exemplo, considerar que por «perto» se entende um

## PASSO 5: Borracha

__Desenhar linhas é legal, mas às vezes também é preciso apagar linhas para corrigir erros.__ 
Nós podemos fazer isso com uma nova ferramenta do lápis que desenha na cor cinza (a mesma cor que o fundo).

Adicione um novo objeto para selecionar a borracha. Use __recurso/borracha__, 
diminua a borracha de tamanho para caber na parte de baixo do Palco. 
Ele deve funcionar da mesma maneira que os outros botões de seleção de cor, anunciando uma mensagem de borracha.

O lápis deve ouvir a mensagem __borracha_ e mudar a cor da caneta para cinza 
(lembre-se que você pode usar o __conta-gotas__ para selecionar a cor do plano de fundo). 
Você também precisa de um novo traje para representar a ferramenta borracha: use a mesma imagem __recursos/borracha__. 
__Lembre-se de redefinir o centro do traje.__

### Teste o projeto
__Clique na bandeira verde.__

A borracha apaga as linhas? Funciona até as bordas? Você pode alternar entre borracha e as outras cores de caneta?

Salve o projeto

##PASSO 6: Carimbando

A próxima coisa a acrescentar é uma ferramenta de carimbo, para carimbar imagens no desenho.


1. Adicione um novo objeto, usando qualquer imagem ou traje que você quiser. 
Encolha o objeto e coloque-o na parte de baixo da tela, ao lado das outras ferramentas. 
Quando esse objeto for clicado, ele deve anunciar __carimbo__.
2. Adicione um novo traje para o lápis, o mesmo que você escolheu para o botão __carimbo__.
3. Selecione o objeto caneta e crie uma nova variável chamada __usando caneta__ __para este objeto apenas__. 
Usaremos esta variável para controlar se estamos desenhando ou carimbando.
4. Adicione um novo objeto para ouvir à mensagem __carimbo__. 
É preciso definir o traje para a carimbo e definir a variável __usando caneta__ para __falso__.
5. Altere os outros comandos que respondem às mensagens da ferramenta de seleção (vermelho, verde, azul e borracha), 
de modo que cada um defina o __usando caneta__ como __verdadeiro__.
6. Finalmente, vamos verificar essa variável __quando o botão do mouse é pressionado__ para ver se devemos desenhar ou carimbar.
Se o "usando caneta" = verdadeiro devemos usar o __abaixe a caneta__ já existente, senão devemos carimbar.

##Teste o projeto
__Clique na bandeira verde.__

A ferramenta carimbo funciona corretamente?

O que acontece quando você usa as cores do lápis?

Salve o projeto

__Parabéns, você completou os passos básicos deste projeto.
Experimente estes desafios!__

## Desafio 1: Caneta Arco-Íris

Vamos adicionar umo lápis especial que pinta nas cores do arco-íris. 
É algo que você não pode fazer com canetas e lápis comuns, por isso é bom para mostrar como desenhar em um computador permite 
fazer coisas diferentes. O segredo é usar o bloco __mude a cor da caneta por__.

Primeiro, adicione um objeto para o botão  arco-íris e o traje arco-íris para o lápis:

1. Crie um novo objeto ao lado de todos os outros objetos de seleção de cor do lápis. 
Use o traje recursos/botão-arco-íris e faça ele anunciar arco-íris quando clicado.
2. Adicione recursos/lápis-arco-lápis para o objeto lápis.

Você pode adicionar os blocos para mudar a cor da caneta muitas vezes por segundo para dar o efeito arco-íris 
(Mudar por 5 a cada 0,05 segundo funciona bem, mas você pode experimentar valores diferentes). 
O cartão de cronômetro do Scratch mostra como você pode fazer algo mudar de tempos em tempos. 
Use um bloco __mude a cor da caneta por (5)__, em vez do __mude [temporizador] por (-1)__ como é o caso do cartão.

Você também precisa controlar esta repetição para que ele só mude a cor da caneta quando o lápis arco-íris estiver selecionado, 
se você não fizer isso todas as cores terão um efeito arco-íris! 
Você pode fazer isso de uma forma semelhante à forma como mudamos entre os modos __carimbo__ e __caneta normal__. 
Você precisa criar uma variável chamada __mudar-arco-iris__ que tem o valor verdadeiro quando você quiser um efeito arco-íris e falso
 caso contrário. Cada vez que o lápis ouve a mensagem relacionada a uma ferramenta de desenho, 
 ela deve mudar a variável __mudar-arco-iris__ de acordo com cada caso.

Use o que você aprendeu com o carimbo no passo acima para controlar o efeito arco-íris.
 O bloco de comandos que ouve às mensagens ferramenta de seleção irá mudar duas variáveis: __usando caneta__ e __mudar-arco-iris__.

### Teste o projeto
__Clique na bandeira verde.__

A ferramenta do arco-íris funciona corretamente?

O que acontece quando você voltar a usar uma das ferramentas normais do lápis?

Salve o projeto

## Desafio 2: Atalhos de teclado

Ao invés de usar os objetos de seleção de ferramenta na parte de baixo do palco, 
você pode usar o teclado para selecionar as diferentes ferramentas.
Você pode usar o bloco __quando tecla [] pressionada__ ​​para reagir ao teclado. 
Para cada tecla que você quiser usar, você vai precisar de outro bloco __quando tecla [] pressionada__, 
que anuncia a mesma mensagem que o respectivo objeto de seleção de ferramenta faz quando clicado. Adicione esses comandos para o palco.

Nós usamos esses atalhos:

* Limpar - a
* Apagar - e
* Caneta Vermelha - r
* Caneta azul - b
* Caneta Amarela - y
* Caneta Verde - g
* Caneta arco-íris - w
* Carimbo - s

### Teste o projeto
__Clique na bandeira verde.__

Todos os atalhos de teclado estão corretos? Cada uma das ferramentas funciona corretamente quando você seleciona com o teclado?
 As ferramentas ainda são selecionadas corretamente usando os botões no palco?

Salve o projeto

## Desafio 3: Pequeno e Grande
Outra característica que a maioria dos pacotes de desenho tem é a capacidade de alterar o
tamanho do lápis. Vamos adicionar isso.
Há uma complicação: às vezes o redimensionamento precisa mudar o tamanho da caneta e às vezes ela precisa mudar o 
tamanho do traje do objeto lápis. Depende se você estiver usando a caneta ou o carimbo.

Crie dois objetos de seleção de ferramenta, chamados de maior e menor. 
Eles devem usar recursos/botão-maior e recursos/botão-menor e devem anunciar as mensagens maior e menor.

O objeto lápis pode ouvir às mensagens mudando o tamanho da caneta por 1 ou o tamanho do traje por 10, 
dependendo do valor do modo de lápis (use um bloco __se..senão__, parecido com o usado para abaixar a caneta ou carimbar)
Não esqueça os atalhos de teclado para as ferramentas  maior e menor. Nós usamos as setas para cima e para baixo.

Salve o projeto

O que você deve ter notado é que a mudança de tamanho do carimbo também altera o tamanho da caneta na tela quando você muda para a ferramenta.
Para impedir isso, você precisa definir o tamanho de 100% cada vez que você mudar para uma ferramenta de caneta. 
Desse modo as ferramentas vão aparecer com o tamanho certo.

Para torná-lo ainda melhor, você pode fazer com que o carimbo lembre o tamanho que tinha antes de você ter selecionado a caneta. 
Assim ele poderá voltar ao tamanho anterior quando você selecionar o carimbo novamente. 
A maneira mais fácil de fazer isso é criar uma nova variável chamada __tamanho do carimbo__, 
que é atualizada com o tamanho atual cada vez que o carimbo é redimensionada. 
Quando a ferramenta carimbo é selecionada, ela pode mudar o seu tamanho usando o valor desta variável.


##Teste o projeto
__Clique na bandeira verde.__

O controle de tamanho funciona para a caneta?

O que acontece se você mudar para o carimbo, alterar o tamanho e, em seguida, voltar para a caneta?

Salve o projeto


__Parabéns você terminou, agora você pode desfrutar do jogo!__


Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ na barra de menu!
