Nível 1 

#Fogo de artifício

__Introdução:__
Neste projeto vamos criar um espectáculo de fogo de artifício nos céus de uma
cidade.

##PASSO 1: Disparar um foguete que sobe na direcção do ponteiro do rato

__Vamos importar as diferentes imagens para o jogo__

1. Cria um novo projeto Scratch. Remove o actor gato clicando nele com o botão
direito do rato e carregando em «»remover.

2. Clica no palco, à esquerda da área «Actores» e depois clica no separador
«Cenários». Importa o cenário «Exterior/city-with-water» e muda-lhe o nome para
«cidade com água». Aproveita para remover o cenário em branco.

3. Na área «Actores», usa o botão «Carregar actor a partir de arquivo» para
adicionares ao projecto um novo actor chamado «o foguete». Usa a imagem
«Recursos/foguete.png».

4. Faz com que o foguete se esconda quando a bandeira verde for clicada.

5. Queremos que o foguete suba em direção ao ponteiro do rato quando a tecla
espaço for pressionada. Adiciona um comando [Quando alguém pressionar a tecla
[espaço ▼]] e adiciona sob esse bloco comandos para fazer o foguete mostrar-se e
deslizar na direcção do ponteiro do rato:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	[fim do guião]

	Quando alguém pressionar a tecla [espaço ▼]
	mostra-te
	desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato))
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde, posiciona o ponteiro do rato sobre o palco e
pressiona a barra de espaço.__ O foguete aparece e eleva-se em direção ao
ponteiro do rato? O que acontece se moveres o rato e pressionares de novo a
barra de espaço?

6. Os foguetes não costumam andar de lado. Vamos fazer com que o foguete comece
sempre na parte de baixo do palco, alinhado com o ponteiro do rato. Antes de
fazer o foguete aparecer, usa o comando [vai para as coordenadas (x: (), y: ())]
para fazer o foguete ir verticalmente para a parte de baixo do palco, mas
horizontalmente para a coordenada x do rato.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	[fim do guião]

	Quando alguém pressionar a tecla [espaço ▼]
	vai para as coordenadas (x: (a coordenada x do rato), y: (-200))
	mostra-te
	desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato))
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde, posiciona o ponteiro do rato sobre o palco e
pressiona a barra de espaço.__ O foguete aparece na base do palco e eleva-se em
direção ao ponteiro do rato? O que acontece se moveres o rato e pressionares de
novo a barra de espaço?

7. Finalmente, vamos usar o botão do rato em vez da barra de espaço. Para isso,
envolvemos o nosso guião pelo comando [se <o botão do rato está pressionado>,
[]], que por sua vez envolvemos pelo comando [repete para sempre, []]. Depois,
trocamos o bloco [Quando alguém pressionar a tecla [espaço ▼]] pelo bloco
[Quando alguém clicar em A BANDEIRA VERDE]. Finalmente, asseguramo-nos de que o
foguete começa escondido acrescentando o comando [esconde-te] ao início do
guião. Uma vez que o outro guião do foguete se tornou redundante, podemos
removê-lo.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete para sempre,
		se <o botão do rato está pressionado>, então
			vai para as coordenadas (x: (a coordenada x do rato), y: (-200))
			mostra-te
			desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato)) 
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde e, em seguida, clica sobre o palco. Clica novamente
noutro ponto do palco.__

###Coisas a experimentar

1. Tenta alterar o local onde o foguete se posiciona antes de se lançar para que
ele se eleve com alguma inclinação.

2. Tenta fazer uns foguetes mais lentos ou mais rápidos que outros.

__Para parar, carrega no sinal de _stop_.__

##PASSO 2: Fazer o foguete explodir

1. O primeiro passo para fazer o foguete explodir é fazê-lo tocar o som de
explosão em «Recursos\lançamento e explosão.wav» antes de ele se começar a mover
e fazê-lo desaparecer quando atingir a posição do ponteiro do rato quando foi
clicado.Para importar o som, vai ao separador «Sons» do actor «o foguete» e
clica no botão «Carregar som a partir de arquivo». Aproveita para remover o som
«miau».

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete para sempre,
		se <o botão do rato está pressionado>, então
			vai para as coordenadas (x: (a coordenada x do rato), y: (-200))
			toca o som [lançamento e explosão ▼]
			mostra-te
			desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato))
			esconde-te
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

2. Em seguida, faz o foguete difundir uma nova mensagem quando explodir. Esta mensagem será recebida e tratada mais tarde.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete para sempre,
		se <o botão do rato está pressionado>, então
			vai para as coordenadas (x: (a coordenada x do rato), y: (-200))
			toca o som [lançamento e explosão ▼]
			mostra-te
			desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato))
			esconde-te
			difunde a mensagem [Eu, foguete, explodi! ▼]
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__  Certifica-te de que o foguete faz o barulho de
lançamento e explosão e que desaparece quando atinge a posição do ponteiro do
rato quando este foi clicado.

3. Importa um novo actor a partir do arquivo «Recursos/a explosão 1.png». Altera o seu nome para «a explosão».

4. Este novo actor deve começar por se esconder, logo que o jogo começar. Depois, sempre que receber a mensagem «Eu, foguete, explodi!», a explosão deve mover-se para a posição do foguete, pelo que usamos o comando [vai para a posição de [o foguete ▼]]. Depois, explosão deve aparecer e, um segundo depois, voltar a desaparecer.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	[fim do guião]

	Quando receberes a mensagem [Eu, foguete, explodi! ▼]
	vai para a posição de [o foguete ▼]
	mostra-te
	espera (1) s
	esconde-te
	[fim do guião]
```

###Testa o teu projeto

__Lança um novo foguete.__ Quando explode, o foguete é substituído pela
representação da explosão? O que acontece se mantiveres o botão do rato
pressionado enquanto o moves? (Não se preocupe, corrigiremos o problema mais
tarde).

##PASSO 3: Fazer com que cada explosão seja única

1. Podemos fazer com que cada explosão seja diferente usando o comando [altera o
teu efeito [cor ▼] para ()], indicando um valor aleatório entre 1 e 200 para
esse efeito. Devemos alterar o efeito de cor antes de mostrar a explosão.

```scratch
	Quando receberes a mensagem [Eu, foguete, explodi! ▼]
	altera o teu efeito [cor ▼] para (um valor ao acaso entre (1) e (200))
	vai para a posição de [o foguete ▼]
	mostra-te
	espera (1) s
	esconde-te
	[fim do guião]
```

### Testa o teu projeto

__Clica na bandeira verde.__ Lança vários foguetes. Cada explosão tem uma cor
diferente?

2. Adiciona algumas representações diferentes da explosão usando as imagens que
estão nos arquivos «Recursos/a explosão 2.png» e «Recursos/a explosão 3.png».
Muda os nomes dos três trajes para «explosão 1», «explosão 2» e «explosão 3».
Altera o guião para, antes de mostrar a explosão, passar para o traje seguinte.

```scratch
	Quando receberes a mensagem [Eu, foguete, explodi! ▼]
	passa para o próximo traje
	altera o teu efeito [cor ▼] para (um valor ao acaso entre (1) e (200))
	vai para a posição de [o foguete ▼]
	mostra-te
	espera (1) s
	esconde-te
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde.__ Lança vários foguetes. Cada foguete tem uma
representação diferente para a sua explosão?

3. Finalmente, vamos fazer a explosão crescer ao longo do tempo em vez de a
fazer simplesmente aparecer. Em vez de esperar um segundo, faz reduz o tamanho
do actor para 5% antes de o mostrares e, em seguida, depois de ser mostrado,
adiciona cinquenta vezes 2% ao tamanho do actor usando um bloco de repetição.

```scratch
	Quando receberes a mensagem [Eu, foguete, explodi! ▼]
	passa para o próximo traje
	altera o teu efeito [cor ▼] para (um valor ao acaso entre (1) e (200))
	vai para a posição de [o foguete ▼]
	altera o teu tamanho para (5) %
	mostra-te
	repete (50) vezes
		adiciona (2) % ao teu tamanho
	[fim do comando «repete vezes»]
	esconde-te
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde.__ Lança um foguete. A representação da explosão vai
crescendo lentamente a partir do centro do foguete?

###Coisas a experimentar

Que tal tentares fazer cada explosão ainda mais original, alterando o tamanho e
a velocidade de crescimento da explosão?

##PASSO 4: Correcção do problema na difusão da mensagem anunciando a explosão 

Lembras-te que tínhamos um erro quando mantínhamos pressionado o botão do rato?
Isso ocorre porque, mal o foguete difunde a mensagem anunciando a sua explosão,
o ciclo repete-se e uma nova mensagem é difundida, antes de se ter terminado de
processar a mensagem anterior.

1. Para corrigir este erro, podemos substituir o comando [difunde a mensagem
[Eu, foguete, explodi! ▼]] pelo comando [difunde a mensagem [Eu, foguete,
explodi! ▼] e espera]. Desta forma, o ciclo não se repetirá até que a explosão
termine de se mostrar.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete para sempre,
		se <o botão do rato está pressionado>, então
			vai para as coordenadas (x: (a coordenada x do rato), y: (-200))
			toca o som [lançamento e explosão ▼]
			mostra-te
			desliza em (1) s para as coordenadas (x: (a coordenada x do rato), y: (a coordenada y do rato))
			esconde-te
			difunde a mensagem [Eu, foguete, explodi! ▼] e espera
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde e em seguida, pressiona o botão do rato sobre o palco
sem o largares.__ A explosão aparece no lugar certo e na altura certa?

