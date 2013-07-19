Nível 1

#Félix & Herbert

__Introdução:__
Vamos fazer um jogo da apanhada com o gato Félix e o rato Herberto. 
Tu controlas o Herberto com o rato do computador e tentas fugir do gato Félix. 
Quanto mais tempo ficares sem ser apanhado, mais pontos ganharás. 
Atenção! Se fores apanhado, perderás pontos!

##PASSO 1: O Félix persegue o ponteiro do rato do computador
Marca o teu progresso nos quadrados abaixo.

1. Cria um novo projecto. 

2. Clica em «o palco» à esquerda da área «Actores», debaixo do palco. Depois,
clica no separador «Cenários», clica no ícone «Escolher cenário a partir da
biblioteca» debaixo de «Novo cenário» e escolhe o cenário «Interior/hall».

3. Clica no cenário «backdrop1» e remove-o clicando na cruz que surge no seu
canto superior direito.

4. Clica no gato Scratch na área «Actores» e depois clica na bola azul com um
«i» que surge no seu canto superior esquerdo. Muda o nome do actor de «Sprite1»
para «o Félix».

5. Certifica-te de que o estilo de rotação de «o Félix» é «olha apenas para a
esquerda e para a direita». Para isso, carrega na seta horizontal dupla que está
abaixo do nome que acabaste de alterar.

6. Carrega na bola azul com o triângulo apontando para a esquerda.

7. Mantém «o Félix» seleccionado na área «Actores» e clica no separador
«Guiões».

8. Arrasta para a área dos guiões, a partir das paletes de blocos à sua
esquerda, os comandos que se seguem, encaixando-os:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (10) passos
		passa para o teu próximo traje
		toca a percussão (10 ▼) durante (0.3) tempos
	[fim do comando «repete para sempre»]
	[fim do guião]
```
		
###Testa o teu projeto

__Clica na bandeira verde.__ O Félix está a perseguir o ponteiro do rato? Parece
andar enquanto se movimenta? A velocidade com que anda é correcta?

__Para parar, carrega no sinal de _stop_.__

##PASSO 2: O Félix persegue o Herberto

__Agora vamos fazer com que o Félix persiga o Herberto em vez de perseguir o
rato do computador.__

1. Cria um novo actor, clicando no ícone «Escolher actor a partir da biblioteca»
à direita de «Novo actor» e escolhendo o actor «Animais/Mouse1».

2. Altera o nome do novo actor para para «o Herberto».

3. Certifica-te de que o estilo de rotação do Herberto é «olha apenas para a
esquerda e para a direita».

4. Clica no separador «Trajes», clica no traje «mouse2» e, no canto superior
esquerdo do editor de pintura, altera o nome do traje de «mouse2» para «vivo,
de cima».

5. Ainda no editor de pintura, selecciona a imagem do rato visto de cima ícone
e, arrastando um dos quadrados nos cantos do retângulo envolvente, diminui o
tamanho do Herberto até ele ficar com um tamanho apropriado, no palco,
relativamente ao Félix.

6. Mantém «o Herberto» seleccionado na área «Actores» e clica no separador
«Guiões».

7. Arrasta para a área dos guiões, a partir das paletes de blocos à sua
esquerda, os comandos que se seguem, encaixando-os:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		vai para a posição de [o ponteiro do rato ▼]
		aponta em direcção a [o Félix ▼]		
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde.__ O Herberto move-se com o ponteiro do rato? O Félix
persegue o Herberto?

__Para parar, carrega no sinal de _stop_.__

##PASSO 3: O Félix diz «Apanhei-te!»

__Vamos fazer com que o Félix nos avise quando apanhar o Herberto__

1. Modifica o guião do Félix para que fique assim:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
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

###Testa o teu projeto

__Clica na bandeira verde.__ O Félix avisa quando apanha o Herberto?

##PASSO 4: O Herberto transforma-se num fantasma

__Em vez de dizer alguma coisa, queremos que o Herberto se transforme num
fantasma quando for apanhado.__

1. Modifica o guião do Félix para que difunda uma mensagem quando apanhar o
Herberto (tens de criar a mensagem, escolhendo «uma nova mensagem» no menu do
comando de difusão):

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (10) passos
		passa para o teu próximo traje
		toca a percussão (10 ▼) durante (0.3) tempos
		se <estás a tocar em [o Herberto ▼]>, então
			difunde a mensagem [Eu, Félix, apanhei o Herberto! ▼]
			toca a percussão (5 ▼) durante (0.3) tempos
			espera (1) s
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

2. Clica sobre o actor «o Herberto», vai até o separador trajes, clica no
ícone «Escolher traje a partir da biblioteca» abaixo de «Novo traje» e
escolhe o traje «Fantasia/ghost2-a».

3. Reduz o tamanho do novo traje no editor de pintura de modo a poder
representar o fantasma do Herberto.

4. Muda o nome do novo traje do Herberto de «ghost2-a» para «morto, de
lado».

5. Clica sobre o traje «vivo, de cima».

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
	
###Testa o teu projeto

__Clica na bandeira verde.__ O Herberto transforma-se brevemente num fantasma
quando é apanhado? O Félix toca o som certo no altura certo? O Félix fica quieto
o tempo suficiente para o Herberto fugir?

##PASSO 5: Contam-se os pontos

__Vamos criar um painel de pontuação para sabermos com nos corre o jogo. A
pontuação começa em zero e aumenta um ponto a cada segundo que passa.  Quando o
Félix apanha o Herberto o jogador perde cem pontos.__

1. Clica em «Dados» no separador «Guiões» e carrega no botão «Criar uma
Variável». Cria uma variável chamada «a pontuação», mantendo selecionada a opção
«Para todos os actores».

2. Clica no objecto «o palco» e cria estes dois guiões na área de guiões do
palco:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
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

###Testa o teu projeto

__Clica na bandeira verde.__ A pontuação aumenta um ponto a cada segundo? A
pontuação diminui 100 pontos quando o Herberto é apanhado? O que acontece quando
o Herberto é apanhado antes que de a pontuação chegar a 100? A pontuação volta a
zero quando começa um novo jogo?

__Carrega no botão «Ver a página do projecto».__

__Parabéns, acabas de criar o teu primeiro jogo!__

Não te esqueças que podes partilhar o teu jogo com todos os Scratchadores
carregando no botão «Partilha»!
