---
title: Robot Falador
level: Scratch 1
language: pt-PT
stylesheet: scratch
embeds: "*.png"
materials: ["Recursos Clube Líder/*"]
...

# Introdução { .intro }

Vais aprender como programar o teu próprio robot que fala!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26762091/?autostart=false" frameborder="0"></iframe>
  <img src="chatbot-final.png">
</div>

# 1ºPaso: O teu robot falador { .activity }

## Lista de tarefas da atividade { .check }

+ Antes de começar a criar o teu robot falador, precisa e decidir qual vai ser a sua personalidade.
	+ Como se chama?
	+ Onde mora?
	+É feliz? Sério? Divertido? Tímido? Amigável?

+ Cria um novo projeto no Scratch e apaga o objeto gato para que o teu projeto fique vazio. Podes encontrar o editor online em <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Escolhe um dos personagens deste objeto e insere o ao teu projeto:

	![screenshot](chatbot-characters.png)

+ Escolhe um palco que fique bem com a personalidade do teu robot falador. Aqui tens um exemplo, mas o teu palco pode ser diferente deste:

	![screenshot](chatbot-sprite.png)

## Guarda o teu projeto { .save }

# 2ºPasso:  Um robot que fala { .activity }

Agora que já tens um robot falador com personalidade, vamos programa lo para que te fale.

## Lista de tarefas da atividade { .check }

+ Faz clique na personagem do teu robot falador e insere este código:

	```blocks
		when this sprite clicked
		ask [Hey! What's your name?] and wait
		say [What a lovely name!] for (2) secs
	```

+ Faz clique no teu robot falador para experimenta lo. Depois de que te pergunte o teu nome, escreve o na caixa de texto que aparece na parte inferior do cenário.

	![screenshot](chatbot-text.png)

+ O teu robot falador respondera te `Que nome tão lindo!` . Podes personalizar a resposta do teu robot falador usando a resposta do usuário. Muda o código do robot falador para este:

	```blocks
		when this sprite clicked
		ask [Hey! What's your name?] and wait
		say <join [Hi] (answer)> for (2) secs
	```

	Para criar este ultimo bloco, primeiro terás que selecionar um bloco verde `unir` {.blockoperators} , e arrasta lo sobre o bloco `dizer` {.blocklooks} block.

	![screenshot](chatbot-join.png)

	Podes mudar o  `hello` por `olá`, e arrastar o bloco azul  `resposta` {.blocksensing} (da seção “Sensores”) sobre o texto `world`.

	![screenshot](chatbot-answer.png)

+ Prova este novo programa. Funciona como esperavas? Podes solucionar os problemas que vês? (Dica: podes tentar inserir um espaço em algum lugar!)

+ Podes querer guardar o nome do usuário numa variável para o poderes usar de novo no futuro. Cria uma nova variável que se chame  `nome` {.blockdata}. Se não te lembras como se faz o projeto “Globos” pode ajudar te.

+ A informação que escreves te já esta armazenada numa variável especial chamada  `resposta` {.blocksensing}. Vai a seção dos blocos sensores e faz clique no bloque de resposta para que apareça uma marca de verificação. O valor atual na variável `resposta` {.blocksensing} deveria de aparecer na parte superior esquerda do cenário.

+ Uma vez tenhas criado a tua nova variável, verifica que o código do teu robot falador seja igual a este:

	```blocks
		when this sprite clicked
		ask [Hey! What's your name?] and wait
		set [name v] to (answer)
		say <join [Hi ] (name)> for (2) secs
	```

+ Se experimentares o programa mais uma vez veras que a resposta fica guardada na variável `nome` {.blockdata} , e que aparece na parte superior esquerda do cenário. A variável `nome` {.blockdata} deveria agora ter o mesmo valor que a variável  `resposta` {.blocksensing} .

	![screenshot](chatbot-variable.png)

	 Se preferes não ver as variáveis no cenário, podes esconde la desativando a marca de verificação que se encontra junto do nome da variável, na janela programas.

## Guarda o teu projeto { .save }

## Desafio: Mais perguntas { .challenge }

Programa o teu robot falador para que faça outra pergunta. Podes guardar a resposta numa variável?

![screenshot](chatbot-question.png)

## Guarda o teu projeto { .save }

# 3ºPasso: Tomar decisões { .activity }

Podes programar o teu robot falador para que escolha o que pretende fazer, em função das respostas do usuário.

## Lista de tarefas da atividade { .check }

+ Vamos fazer que o teu robot falador faça ao usuário uma pergunta com resposta `sim` ou `não`.
Exemplo:

	```blocks
		when this sprite clicked
		ask [Hey! What's your name?] and wait
		set [name v] to (answer)
		say <join [Hi ] (name)> for (2) secs
		ask <join [Are you OK ] (name)> and wait
		if ((answer)=[yes]) then
			say [That's great to hear!] for (2) secs
		end
	```

	Repara que agora que guardas te o nome do usuário numa variável, podes usa lo tantas vezes como quiseres.

+ Para experimentar se o programa funciona bem, terás que experimenta lo duas vezes, numa a resposta devera ser `não` e na outra a resposta devera ser `sim`. O robot falador só devera te responder `se` {.blockcontrol} a tua resposta for `sim`.

+ O problema é que o teu robot falador não te responde se a resposta for `não`. Podes solucionar este problema mudando o bloco `se` {.blockcontrol} por um bloco `se/senão` {.blockcontrol} , para que o teu novo código seja como este:

	```blocks
		when this sprite clicked
		ask [Hey! What's your name?] and wait
		set [name v] to (answer)
		say <join [Hi ] (name)> for (2) secs
		ask <join [Are you OK ] (name)> and wait
		if ((answer)=[yes]) then
			say [That's great to hear!] for (2) secs
		else
			say [Oh no!] for (2) secs
		end
	```

+ Se experimentares o teu código, repararas que agora obténs uma resposta se respoderes `sim` ou `não`. O teu robot falador deveria responder `Fico feliz ao saber que estas bem!` quando respondes `sim`, mas respondera `Oh não!` Se responderes `não`.

	![screenshot](chatbot-else.png)

+ Podes por qualquer código dentro de um bloco `se` {.blockcontrol} ou `senão` {.blockcontrol} sem ser código para que o teu robot fale. Por exemplo, podes mudar o traje do teu robot falador para que este de acordo com a sua resposta.


	Para usares estes trajes como parte da resposta do teu robô falador, insere este código:

	![screenshot](chatbot-costumes-code.png)

+ Experimenta o teu programa, e deveras ver como a cara do teu robot muda conforme a resposta que escreveres.

	![screenshot](chatbot-face.png)

## Guarda o teu projeto { .save }

## Desafio: Mais decisões { .challenge }

Programa o teu robot falador para que faça mais perguntas, cujas respostas `sim` ou `não` answer. Podes fazer que o teu robot responda á resposta?

![screenshot](chatbot-joke.png)

## Guarda o teu projeto { .save }

# 4ºPasso: Mudar localização { .activity }

Também podes programar o teu robot falador para que mude a sua localização.

## Lista de tarefas da atividade: { .check }

+ Insere outro fundo ao teu cenário, por exemplo o fundo ‘moon’ (lua).

	![screenshot](chatbot-moon.png)

+ Agora podes programar o teu robot falador para que troque de local inserindo este código:

	```blocks
		ask [I'm going to the moon. Do you want to come with me?] and wait
		if ((answer) = [yes]) then
			switch backdrop to [moon v]
		end
	```

+ Também deves de ter a certeza que o teu robot falador este fora quando comeces a falar com ele. Insere este bloco ao principio do código do teu robot falador:

	![screenshot](chatbot-outside.png)

+ Experimenta o teu programa, e responde sim quando te perguntar se queres ir a lua. O local onde se encontra o teu robot falador deveria de mudar.

	![screenshot](chatbot-backdrop.png)

+ Muda o local do teu robot falador quando escreves `não`? E o que acontece se escreveres `Não estou seguro`?

+ Também podes agregar este código dentro do teu bloco `se` {.blockcontrol} , para fazer que o teu robot falador salte 4 vezes se a resposta for `sim`:

	```scratch
	repeat (4)
		change y by (10)
		wait (0.1) secs
		change y by (-10)
		wait (0.1) secs
	end
	```

	![screenshot](chatbot-loop.png)

+ Prova o teu código uma vez mais. O teu robot falador salta quando respondes `sim`?

## Guarda o teu projeto { .save }

## Desafio: Cria o teu próprio robot falador {.challenge}
Utiliza tudo o que aprendes te para acabar de criar o teu robot falador interativo. Aqui tens algumas ideias:

![screenshot](chatbot-ideas.png)

Quando acabes de criar o te robot falador, faz que os teus amigos falem com ele! Encontraram algum problema?

## Guarda o teu projeto { .save }
