---
title: Apanha os pontos
level: Scratch 2
language: pt-PT
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos Clube Líder/*","Recursos do Projeto/*"]
beta: true
...

# Introdução { .intro }

Neste projeto vais aprender a criar um jogo no qual terás que fazer coincidir pontos de cores com a parte correta do controlador.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/44942820/?autostart=false" frameborder="0"></iframe>
  <img src="dots-final.png">
</div>

# 1ºPasso: Criar um controlador  { .activity }

Começamos criando um controlador, que utilizaremos para apanhar os pontos.

## Lista de tarefas da atividade { .check }

+ Cria um novo projeto no Scratch, e apaga o objeto gato de maneira a que o projeto fique totalmente vazio. Podes encontrar o editor online do Scratch em <as href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Se o líder do teu clube te deu um portefólio de “Recursos”, faz clique em “Carregar objetos a partir do arquivo” e insere a imagem ‘controller.svg’. Terás que mexer o objeto até ao centro do cenário.

	![screenshot](dots-controller.png)

	Se não tiveres esta imagem, podes desenha la tu!

+ Faz que o controlador gire para a direita quando for pressionada a tecla da seta para a direita.

	```blocks
		when flag clicked
		forever
			if <key [right arrow v] pressed?> then
				turn right (3) degrees
			end
		end
	```
+ Prova o teu controlador. Deveria girar para a direita.

## Guarda o teu projeto { .save }

## Desafio: Girar para a esquerda {.challenge}
Podes fazer que o controlador gire para a esquerda quando for pressionada a tecla da seta para a esquerda?

## Guarda o teu projeto { .save }

# 2ºPasso: Apanhar pontos { .activity }

Vamos inserir alguns pontos que o jogador terá de apanhar com o controlador.

## Lista de tarefas da atividade { .check }

+ Cria um novo objeto chamado 'vermelho'. Este objeto devera ser um pequeno ponto vermelho.

	![screenshot](dots-red.png)

+ Insere estas instruções ao objeto ponto 'vermelho', para que seja criado um clone do ponto a cada determinado segundo.

	```blocks
		when flag clicked
		wait (2) secs
		forever
			create clone of [myself v]
			wait (pick random (5) to (10)) secs
		end
	```

+ Quando criamos um clone queremos que apareça numa das 4 esquinas do cenário.

	![screenshot](dots-start.png)

	Para fazer isto, primeiro terás de criar uma nova lista chamada `posições de inicio ` {.blockdata} e fazer clique em `(+)` para inserir os valores  `-180` e `180`.

	![screenshot](dots-list.png)

+ Podes usar estos dois elementos da lista para escolher a esquina do cenário ao azar. Insere este código ao objeto ‘ponto’, para que todos os novos clones vão até uma esquina ao azar e a seguir se mexam lentamente até o controlador.

	```blocks
		when I start as a clone
		go to x: (item (random v) of [start positions v]) y: (item (random v) of [start positions v])
		point towards [controller v]
		show
		repeat until <touching [controller v]?>
			move (1) steps
		end
	```

	Neste código escolhe `-180` ou `180` para as posições x _e_ y o que significa que todos os clones começaram numa das esquinas do cenário.

+ Experimenta o teu projeto. Deverias de ver como aparecem muitos pontos vermelhos em cada uma das esquinas do cenário e se mexem lentamente até ao controlador.

	![screenshot](dots-red-test.png)

+ Cria 2 novas variáveis com os nomes `vidas` {.blockdata} e `pontuação` {.blockdata}.

+ Insere código ao cenário para fixar as  `vidas` {.blockdata} a 3 e a `pontuação` {.blockdata} a 0 quando comece o jogo.

+ Terás de inserir instruções no fim do código do ponto vermelho `ao começar como clone` {.blockcontrol} para que some 1 ponto a `pontuação` {.blockdata} do jogador se as cores coincidirem, ou subtraia 1 das `vidas` {.blockdata} do jogador se as cores não coincidirem.

	```blocks
		move (5) steps
		if <touching color [#FF0000]?> then
			change [score v] by (1)
			play sound [pop v]
		else
			change [lives v] by (-1)
			play sound [laser1 v]
		end
		delete this clone
	```

+ Insere este código no fim das instruções do cenário, para que o jogo acabe quando o jogador ficar sem vidas:

	```blocks
		wait until <(lives) < [1]>
		stop [all v]
	```

+ Experimenta o teu jogo para teres a certeza que o código funciona corretamente.

## Guarda o teu projeto { .save }

## Desafio: Mais pontos {.challenge}
Duplica o ponto 'vermelho' duas vezes, e chama aos novos objetos 'amarelo' e 'azul'.

![screenshot](dots-more-dots.png)

Edita estos objetos (incluindo o código), para que a cor de cada um dos pontos tenha de coincidir com a cor correta do controlador. Não te esqueças de experimentar o projeto, e comprova se consegues pontos e perdes vidas quando corresponde, E o jogo não pode ser nem muito fácil nem muito difícil!

![screenshot](dots-all-test.png)

## Guarda o teu projeto { .save }

# 3ºPasso: Aumentar a dificuldade { .activity .new-page}

Vamos fazer que o jogo seja mais difícil dependendo do tempo que o jogador esteja a conseguir sobreviver, reduzindo lentamente o intervalo entre os pontos que aparecem.

## Lista de tarefas da atividade { .check }

+ Cria uma nova variável com o nome `intervalo` {.blockdata}.

+ No cenário, cria um novo código que defina o intervalo num número alto, e que lentamente va reduzindo o valor do intervalo.

	```blocks
		when flag clicked
		set [delay v] to (8)
		repeat until < (delay) = (2)>
			wait (10) secs
			change [delay v] by (-0.5)
		end
	```

	Repara que isto é muito parecido a maneira como funciona um cronómetro num jogo!

+ Para acabar, podes utilizar a variável `intervalo` {.blockdata} no código dos teus pontos vermelho, amarelo e azul. Apaga o código que espera um número ao azar de segundos para criar clones e substitui o pela tua nova variável `intervalo` {.blockdata} :

	```blocks
		wait (delay) secs
	```

+ Experimenta a tua nova variável `intervalo` {.blockdata} , e comprova se o intervalo entre os pontos se vai reduzindo lentamente.
Funciona para os 3 pontos de cores? Podes ver como se reduz o valor da variável `intervalo` {.blockdata} ?

## Guarda o teu projeto { .save }

## Desafio: Pontos que se mexem mais rápido {.challenge}
Podes melhorar o jogo inserindo uma variável de  `velocidade` {.blockdata} , para que os pontos comecem se mexendo 1 passo de cada vez e vão pouco a pouco aumentando a velocidade? Isto funcionara de uma maneira muito parecida a variável  `intervalo` {.blockdata} que utilizamos acima, e podes utilizar esse código como ajuda.

## Guarda o teu projeto { .save }

# 4º Passo: Pontuação mais alta { .activity }

Vamos guardar a pontuação mais alta, para que assim os jogadores possam ver se estão a melhorar.

## Lista de tarefas da atividade { .check }

+ Cria uma nova variável com o nome `pontuação mais alta` {.blockdata}.

+ Faz clique no cenário, e cria um novo bloco personalizado que se chame `verificar pontuação mais alta` {.blockmoreblocks}.

	![screenshot](dots-custom-1.png)

+ Antes de que acabe o jogo insere o teu novo bloco personalizado.

	![screenshot](dots-custom-2.png)

+ Insere este código ao teu bloco personalizado para guardar a `pontuação` {.blockdata} atual como a `pontuação mais alta` {.blockdata} `se` {.blockcontrol} for a pontuação máxima até ao momento:

	```blocks
		define [check high score]
		if <(score) > (high score)> then
			set [high score v] to (score)
		end
	```

## Guarda o teu projeto. { .save }

## Desafio: Melhora o teu jogo! {.challenge}
Tens ideias de como poderias melhorar o teu jogo?
Por exemplo, poderias criar pontos especiais que:

+ dupliquem a pontuação;
+ reduzam a velocidade dos pontos;
+ façam desaparecer o resto dos pontos no ecrã!

## Guarda o teu projeto { .save }

## Desafio: Menu do jogo {.challenge}
Podes inserir um menu com botões ao teu jogo? Poderias inserir um ecrã de instruções, ou um ecrã para mostrar a pontuação mais alta? Se precisas de ajuda com isto, o projeto 'Jogo de calculo mental' pode ser te útil.
