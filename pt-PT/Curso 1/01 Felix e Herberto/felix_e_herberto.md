Nível 1

#Félix & Herbert

__Introdução:__
Vamos fazer um jogo da apanhada com o gato Félix e o rato Herberto. 
Tu controlas o Herberto com o rato do computador e tentas fugir do gato Félix. 
Quanto mais tempo ficares sem ser apanhado, mais pontos ganharás. 
Atenção! Se fores apanhado, perderás pontos!

##PASSO 1: P Félix persegue o ponteiro do rato do computador
Marca o teu progresso nos quadrados abaixo.

1. Cria um novo projecto. 

2. Clica em __o palco__ à esquerda da área __Actores__, debaixo do palco.
Depois, clica no separador __Cenários__, clica no ícone __Escolher cenário a
partir da biblioteca__ debaixo de __Novo cenário__ e escolhe o cenário
__Interior/hall__.

3. Clica no cenário __backdrop1__ e remove-o clicando na cruz que surge no seu
canto superior direito.

4. Clica no gato Scratch na área __Actores__ e depois clica na bola azul com um
«i» que surge no seu canto superior esquerdo. Muda o nome do actor de
__Sprite1__ para __o Félix__.

5. Certifica-te de que o estilo de rotação de __o Félix__ é __olha apenas para a
esquerda e para a direita__. Para isso, carrega na seta horizontal dupla que
está abaixo do nome que acabaste de alterar.

6. Carrega na bola azul com o triângulo apontando para a esquerda.

7. Mantém __o Félix__ seleccionado na área _Actores_ e clica no separador
__Guiões__.

8. Arrasta para a área dos guiões, a partir das paletes de blocos à sua
esquerda, os comandos que se seguem, encaixando-os:

```scratch
	Quando alguém clicar em A BANDEIRA verde
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (10) passos
		passa para o teu próximo traje
		toca a percussão (10 ▼) durante (0.3) tempos
	[fim do comando «repete para sempre»]
	[fim do guião]
```
		
###Testa o projeto

__Clica na bandeira verde.__

O Félix está a perseguir o ponteiro do rato? 

Parece andar enquanto se movimenta? 

A velocidade com que anda é correcta?

__Para parar, carrega no sinal de _stop_.__

##PASSO 2: O Félix persegue o Herberto

__Agora vamos fazer com que o Félix persiga o Herberto em vez de perseguir o
rato do computador.__

1. Cria um novo actor, clicando no ícone __Escolher actor a partir da
biblioteca__ à direita de __Novo actor__ e escolhendo o actor
__Animais/Mouse1__.

2. Altera o nome do novo actor para para __o Herberto__.

3. Certifica-te de que o estilo de rotação do Herberto é __olha apenas para a
esquerda e para a direita__.

4. Clica no separador __Trajes__, clica no traje __mouse2__ e, no canto superior
esquerdo do editor de pintura, altera o nome do traje de __mouse1__ para __vivo,
de cima__.

5. Ainda no editor de pintura, selecciona a imagem do rato visto de cima ícone
e, arrastando um dos quadrados nos cantos do retângulo envolvente, diminui o
tamanho do Herberto até ele ficar com um tamanho apropriado, no palco,
relativamente ao Félix.

6. Mantém __o Herberto__ seleccionado na área _Actores_ e clica no separador
__Guiões__.

7. Arrasta para a área dos guiões, a partir das paletes de blocos à sua
esquerda, os comandos que se seguem, encaixando-os:

```scratch
	Quando alguém clicar em A BANDEIRA verde
	repete para sempre,
		vai para a posição de [o ponteiro do rato ▼]
		aponta em direcção a [o Félix ▼]		
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o projeto
__Clica na bandeira verde.__

O Herberto move-se com o ponteiro do rato?

O Félix está a perseguir o Herberto?

__Para parar, carrega no sinal de _stop_.__

##PASSO 3: O Félix diz «Apanhei-te!»

__Vamos fazer com que o Félix nos avise quando apanhar o Herberto__

1. Modifica o guião do Félix para que fique assim:

```scratch
	Quando alguém clicar em A BANDEIRA verde
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (10) passos
		passa para o teu próximo traje
		toca a percussão (10 ▼) durante (0.3) tempos
		se <estás a tocar em [o Herberto ▼]>, então
			diz [Apanhei-te!] durante (1) s
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o projeto
__Clica na bandeira verde.__

O Félix avisa quando apanha o Herberto?

##PASSO 4: O Herberto transforma-se num fantasma

__Em vez de dizer alguma coisa, vamos fazer com que o Herberto se transforme num
fantasma quando for apanhado.__

1. Modifica o guião do Félix para que difunda uma mensagem quando apanhar o
Herberto (tens de criar a mensagem, escolhendo __uma nova mensagem__ no menu do
comando de difusão):

```scratch
	Quando alguém clicar em A BANDEIRA verde
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (10) passos
		passa para o teu próximo traje
		toca a percussão (10 ▼) durante (0.3) tempos
		se <estás a tocar em [o Herberto ▼]>, então
			difunde a mensagem [Eu, Félix, apanhei o Herberto! ▼]
			toca a percussão (5 ▼) durante (0.2) tempos
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

2. Clica sobre o actor __o Herberto__, vai até o separador trajes, clica no
ícone __Escolher traje a partir da biblioteca__ abaixo de __Novo traje__ e
escolhe o traje __Fantasia/ghost2-a__.

3. Reduz o tamanho do novo traje no editor de pintura de modo a poder
representar o fantasma do Herberto.

4. Muda o nome do novo traje do Herberto de __ghost2-a__ para __morto, de
lado__.

5. Clica sobre o traje `vivo, de cima`.

6. Cria um novo guião para o Herberto, que fará com que se transforme num
fantasma. Este guião ficará junto ao guião já existente para o Herberto.

__Não removas o guião que já existe para o Herberto e que fazem com que ele
persiga o ponteiro do rato!__

```scratch
	Quando receberes a mensagem [Eu, Félix, apanhei o Herberto! ▼]
	muda o teu traje para [morto, de lado ▼]
	espera (0.5) s
	muda o teu traje para [vivo, de cima ▼]	
```	
	
###Testa o projeto

__Clica na bandeira verde.__

O Herberto transforma-se brevemente num fantasma quando é apanhado?

O Félix toca o som certo no altura certo?

O Félix fica parado o tempo suficiente para o Herberto fugir?

##PASSO 5: Contamos os pontos

__Vamos criar um painel de pontuação para sabermos com nos corre o jogo. A
pontuação começa em zero e aumenta um ponto a cada segundo que passa.  Quando o
Félix apanha o Herberto o jogador perde cem pontos.__

1. Clica em __Dados__ no separador __Guiões__ e carrega no botão __Criar uma
Variável__. Cria uma variável chamada __a pontuação__, mantendo selecionada a
opção __Para todos os actores__.

2. Clica no objecto __o palco__ e cria estes dois guiões na área de guiões do
palco:

```scratch
	Quando alguém clicar em A BANDEIRA verde
	altera [a pontuação ▼] para [0]
	repete para sempre,
		espera (1) s
		adiciona a [a pontuação ▼] o valor (1)
	[fim do comando «repete para sempre»]
	[fim do guião]
```

```scratch
	Quando receberes a mensagem [Eu, Félix, apanhei o Herberto! ▼]
	adiciona a [a pontuação ▼] o valor (-100)
	[fim do guião]
```	

###Testa o projeto
__Clica na bandeira verde.__

A pontuação aumenta um ponto a cada segundo?

A pontuação diminui 100 pontos quando o Herberto é apanhado?

O que acontece quando o Herberto é apanhado antes que de a pontuação chegar a
100?

A pontuação volta a zero quando começa um novo jogo?

__Carrega no botão Ver a página do projecto.__

__Parabéns, acabas de criar o teu primeiro jogo!__

Não te esqueças que podes partilhar o teu jogo com todos os Scratchadores
carregando no botão __Partilha__!
