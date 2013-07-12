Nível 2 

#Corrida no deserto

__Introdução:__ Este jogo é uma corrida entre um papagaio e um elefante através do
deserto. O jogo tem dois jogadores, cada um controlando o seu animal. Cada
jogador tem de pressionar uma tecla o mais rápido que conseguir para mover o
seu animal. Ganha quem chegar primeiro à borda do palco.

##PASSO 1: Criar a cena e adicionar os actores

1. Selecciona o palco e adiciona o deserto como cenário. Encontra-lo na pasta
«Natureza» da biblioteca. Altera o nome do novo cenário para «deserto». Remove
o cenário original.

2. Remove o actor gato.

3. Adiciona um novo actor seleccionando o elefante que está na pasta dos
animais da biblioteca. Altera-lhe o nome para «o elefante». Altera os nomes
dos seus trajes para «a andar» e «parado», respectivamente.

4. Adiciona um novo actor seleccionando o papagaio que está na pasta dos
animais da biblioteca. Altera-lhe o nome para «o papagaio». Altera os nomes
dos seus trajes para «asas para cima» e «asas para baixo», respectivamente.

##PASSO 2: Fazer o elefante e o papagaio correrem

Queremos que os actores andem quando pressionarmos a correspondente tecla.

1. Primeiro, selecciona o actor elefante e fá-lo mover-se quatro passos sempre
que pressionares na tecla «E»:

```scratch
	Quando alguém pressionar a tecla [e ▼]
	anda (4) passos
	[fim do guião]
```

2. Em seguida, selecciona o actor papagaio e fá-lo mover-se quatro passos sempre que pressionares na tecla «P»:

```scratch
	Quando alguém pressionar a tecla [p ▼]
	anda (4) passos
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ O elefante e o papagaio andam através do palco quando pressionas «E» e «P», respectivamente?

##PASSO 3: Começando a corrida

Precisamos de uma forma de começar a corrida e de saber quem ganhou. __Primeiro vamos criar um botão de começo.__

1. Adiciona um novo actor a partir da biblioteca. Escolhe «Coisas/Button1».
Altera o seu nome para «o botão de começo». Altera o nome do seu traje para
«normal».

2. Edita o traje do botão adicionando o texto «começar».

3. Agora adiciona um guião ao actor botão para fazer fazer surgir o botão, no
local certo, quando o projecto for iniciado:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	vai para as coordenadas (x: (0), y: (0))
	mostra-te
	[fim do guião]
```

4. Agora queremos que o botão faça uma contagem decrescente começando em 3,
que diga «Partida!» quando terminar a contagem e que finalmente desapareça.
Adiciona um novo guião como se segue:

```scratch
	Quando alguém clicar em ti
	diz [3] durante (1) s
	diz [2] durante (1) s
	diz [1] durante (1) s
	diz [Partida!] durante (1) s
	esconde-te
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ O botão aparece no centro do palco? Quando clicas
no botão, ele faz uma contagem decrescente antes de anunciar a partida e
desaparecer?

Como os corredores só devem poder correr depois de a corrida começar, e como
precisamos de saber quando a corrida acabou, vamos recorrer a uma variável
para guardar o estado do jogo.

5. Adiciona uma variável para todos os objectos chamada «o estado do jogo».
Desmarca a caixa de selecção junto à nova variável para que ela não apareça no
palco. Ou, melhor ainda, mantém a variável no palco por enquanto, para poderes
mais facilmente corrigir algum erro. Logo que tudo esteja a funcionar
correctamente, esconde-a.

6. Agora vamos inicializar a variável «o estado do jogo» com o valor
«esperando» quando o projeto iniciado. Altera o guião iniciado por [Quando
alguém clicar em BANDEIRA VERDE] que criaste anteriormente de modo a ficar
como se segue:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	vai para as coordenadas (x: (0), y: (0))
	mostra-te
	altera [o estado do jogo ▼] para [esperando]
	[fim do guião]
```

7. Em seguida, faz com que a variável «o estado do jogo» seja alterada para
«correndo» assim que a contagem decrescente termine.

8. Agora temos de impedir que o elefante e o papagaio se movam enquanto o valor da variável «o estado do jogo» não for «correndo». 
Clica no actor papagaio e __adiciona ao guião um comando de controlo__ que só deixe o papagaio mover-se se o valor de «o estado do jogo» for «correndo»:

```scratch
	Quando alguém pressionar a tecla [p ▼]
	se &lt;(o estado do jogo) = [correndo]>, então
		anda (4) passos
	[fim do comando «se, então»]
	[fim do guião]
```

9. Agora faz o mesmo para o elefante.

###Testa o teu projecto

__Clica na bandeira verde.__ O elefante e o papagaio correm apenas após o fim
da contagem decrescente?

##PASSO 4: Finalizando a corrida

Queremos saber quem ganha a corrida e reiniciar o jogo quando ele terminar
para que possamos jogar novamente.

1. Altera o guião do papagaio de modo a alterar o valor da variável «o estado do jogo» para «esperando» assim que ele tocar na borda do palco:

```scratch
	Quando alguém pressionar a tecla [p ▼]
	se &lt;(o estado do jogo) = [correndo]>, então
		anda (4) passos
		se &lt;estás a tocar em [a borda ▼]>, então
			altera [o estado do jogo ▼] para [esperando]
		[fim do comando «se, então»]
	[fim do comando «se, então»]
	[fim do guião]
```

2. Agora queremos que o papagaio informe de que ganhou a corrida. Grava um
novo som para o papagaio, que será tocado quando ele ganhar. Vai para o
separador «Sons» do papagaio, remove o som «bird» e, depois, carrega no botão
«Gravar novo som». Usa o editor de som para gravares o som a tocar se o
papagaio vencer a corrida! (Carrega no botão com uma bola para gravar, no
botão com um quadrado para parar e no botão com uma seta para tocar.) Dá ao
novo som um nome apropriado. Por exemplo, «Vitória!».

3. Adiciona comandos que façam o papagaio tocar o som que acabaste de gravar e
que o façam dizer que ganhou a corrida:

```scratch
	Quando alguém pressionar a tecla [p ▼]
	se &lt;(o estado do jogo) = [correndo]>, então
		anda (4) passos
		se &lt;estás a tocar em [a borda ▼]>, então
			altera [o estado do jogo ▼] para [esperando]
			toca o som [Vitória! ▼]
			diz [Vitória!] durante (3) s
		[fim do comando «se, então»]
	[fim do comando «se, então»]
	[fim do guião]
```

4. Repete os passos anteriores para o elefante.

###Testa o teu projecto

Arrasta os corredores para o lado esquerdo do palco. __Clica na bandeira
verde.__ Carrega nas teclas «P» e «E». O papagaio e o elefante mantêm-se
parados? Clica no botão «pressionar». Carrega nas teclas «P» e «E». O papagaio
e o elefante já correm? Carrega numa das teclas para levares um dos corredores
até à borda do palco. Ele canta vitória, quer tocando o som, quer dizendo a
sua mensagem? Repete para o outro corredor.

##PASSO 5: Reiniciando o jogo

Após a corrida terminar, é preciso comunicar aos outros actores que a corrida acabou e reiniciar o jogo para que possamos fazer uma nova corrida.

__O actor vencedor deve avisar todos os outros de que ganhou.__

1. Clica sobre o actor papagaio. Adiciona um bloco que difunde a mensagem «A
corrida acabou!» depois desse actor cantar vitória.

```scratch
	Quando alguém pressionar a tecla [p ▼]
	se &lt;(o estado do jogo) = [correndo]>, então
		anda (4) passos
		se &lt;estás a tocar em [a borda ▼]>, então
			altera [o estado do jogo ▼] para [esperando]
			toca o som [Vitória! ▼]
			diz [Vitória!] durante (3) s
			difunde a mensagem [A corrida acabou! ▼]
		[fim do comando «se, então»]
	[fim do comando «se, então»]
	[fim do guião]
```

2. Faz o mesmo para o actor elefante.

3. Ainda no actor elefante, adiciona um guião que fique à escuta da mensagem
«A corrida acabou!» e, quando a receber, desloque o papagaio de volta à sua
posição inicial (o que acontece se alterares os valores usados para as
coordenadas x e y?):

```scratch
	Quando receberes a mensagem [A corrida acabou! ▼]
	vai para as coordenadas (x: (-150), y: (-80))
	[fim do guião]
```

4. Também queremos inicializar a posição do elefante quando o jogo é iniciado. Adiciona o seguinte guião para que isso aconteça: 

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	vai para as coordenadas (x: (-150), y: (-80))
	[fim do guião]
```

5. Repete os passos anteriores para o actor papagaio, mas usando um valor diferente para a coordenada y: 80.

6. Agora clica no actor botão e adiciona um guião que o faça reaparecer quando
receber a mensagem «A corrida acabou!».

###Testa o teu projecto

__Clica na bandeira verde.__ Consegues jogar com um amigo, um correndo com o
papagaio pressionando «P» e o outro com o elefante pressionando «E»? O jogo
recomeça quando algum dos corredores chega à meta?

##DESAFIO: Adicionando uma tecla de turbo

* __Adiciona uma tecla de turbo__ que cada corredor pode usar apenas uma vez
em cada corrida. Esta tecla move o corredor __30 passos de uma só vez.__ (Usa
a tecla «W» para o elefante e a tecla «O» para o papagaio.)

* __Adiciona um novo traje__ a cada actor com fogo saindo por atrás. Faz com
que os actores mudem para esse traje temporariamente quando a tecla de turbo
é pressionada.

* __Cria um outro som__ para cada personagem que seja tocado quando a tecla de turbo for pressionada.

* __Faz o papagaio bater as asas__ enquanto está na corrida.

###Testa o teu projecto

__Parabéns! Terminaste! Agora podes desfrutar do jogo!__

Não te esqueças que podes partilhar o teu jogo com todos os Scratchadores,
incluindo os teus amigos e os teus familiares, clicando em «Partilhar»!
