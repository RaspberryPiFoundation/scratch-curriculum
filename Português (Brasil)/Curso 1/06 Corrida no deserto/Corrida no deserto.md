
Nível 2 

# Corrida no deserto

__Introdução:__
Este jogo é para dois jogadores. Você corre com um papagaio e um leão através do deserto. 
Cada jogador tem que pressionar uma tecla o mais rápido que puder para mover seu animal. Ganha quem chegar primeiro à borda da tela	.


## PASSO 1: Criando a cena e adicionando personagens

1. Selecione o Palco, e adicione o fundo do deserto.
2. Adicione um novo personagem, selecione o leão que você vai encontrar na pasta __animals__.
3. Adicionar outro personagem, selecione o papagaio que você vai encontrar na pasta __animals__.



## Passo 2: Faça o leão e o papagaio correrem


O personagem deve andar quando pressionarmos uma tecla.


1. Primeiro, selecione o objeto leão e crie o código para fazê-lo mover quatro passos quando você pressiona a tecla 'L'.



		quando a tecla [l ] for pressionada
		mova (4) passos


2. Em seguida, selecione o papagaio e crie o código para mover quatro passos quando pressionar a tecla 'A'.



		quando a tecla [a ] for pressionada
		mova (4) passos


### Teste o projeto
__Clique na bandeira verde.__ 
O leão e papagaio andam pela tela quando você pressiona 'A' e "L"?

Salve o projeto


## PASSO 3: Começando a corrida

Nós precisamos de uma maneira de começar a corrida e também de saber quem ganhou. __Primeiro vamos criar um botão "começar".__

1. Adicione um objeto do arquivo. Escolha a imagem __button__ que está dentro da pasta "things". Renomeie o objeto para __botão__.
2. Edite o traje do botão, e adicionar o texto 'começar' e clique OK. Mova o botão para o meio do palco.
3. Agora adicione o código para fazer aparecer o botão quando o projeto for executado:



		quando BANDEIRA clicado 
		apareça

4. Quando clicarmos no botão vamos fazer uma contagem regressiva começando em 3. Em seguida, dizer _corra!_ e finalmente desaparecer. 
Adicione um outro bloco de comandos como o seguinte:



		quando botão Clicado
		diga (3) por (1) segundos
		diga (2) por (1) segundos
		diga (1) por (1) segundos
		diga (Corra!) por (1) segundos 
		desapareça

### Teste o projeto
__Clique na bandeira verde.__

Quando você clica, o botão faz contagem regressiva antes de desaparecer?

Salve o projeto

Os jogadores só devem poder correr depois que a corrida começou. Nós também precisamos saber quando a corrida acabou. 
Para isso vamos usar variáveis.

5. Adicione uma variável para todos os objetos chamada __correndo__. 
Desmarque a caixa ao lado dela para que ela não apareça no palco.
6. Agora mude _correndo_ para 0 (zero) quando o projeto for executado pela primeira vez. 
Mude o bloco de comandos __quando bandeira clicada__ criado anteriormente, e faça ele parecer com o seguinte:


		quando BANDEIRA clicado 
		apareça
		mude [correndo v] para (0)

7. Em seguida, mude a variável __correndo__ para 1 (um) quando a contagem regressiva acabar.
8. Agora é preciso que o leão e o papagaio somente possam mover quando a variável __correndo__ for 1. 
Clique no papagaio e  __adicione um bloco de comandos__ que só deixa o
papagaio se mover se __correndo = 1__.



		quando a tecla [a ] for pressionada
		se <[correndo v]= (1) >
			mova (4) passos
		fim

9. Agora faça o mesmo para o leão.

### Teste o projeto
__Clique na bandeira verde.__

O leão e o papagaio correm somente após o fim da contagem regressiva?



##PASSO 4: Finalizando a corrida
Queremos saber quem ganhou a corrida e reiniciar o jogo quando acabar para que você possa
jogar novamente.

1. Adicione um bloco de comandos para o papagaio que mude a variável __correndo_ para 0 quando ele tocar a borda da tela.



		quando a tecla [a ] for pressionada
		se <[correndo v]= (1) >
			mova (4) passos
			se <tocando em [borda v]?>
				mude [correndo v] para (0):
			fim
		fim

2. Em seguida, o papagaio deve informar que ele ganhou a corrida. Grave um novo som para o papagaio, que será tocado quando ele ganhar. 
Clique __Sons__ e depois em __gravar__ para gravar o som a ser tocado se o papagaio vencer a corrida!
3. Agora adicione blocos para tocar o som que você gravou e faça com que o papagaio diga que ganhou:



		quando a tecla [a ] for pressionada
		se <[correndo v]= (1) >
			mova (4) passos
			se <tocando em [borda v]?>
				mude [correndo v] para (0)
				toque o som [gravação1]
				diga [O papagaio ganhou!] por (3) segundos 
			fim
		fim

4. Repita os passos anteriores para o leão.

### Teste o projeto
__Clique na bandeira verde.__

Você consegue pressionar o botão __começar__ e correr com as teclas 'A' e 'L'?
Os personagens tocam o som da vitória e dizem se ganharam quando chega o fim da corrida?

Salve o projeto

##PASSO 5: Reiniciando o jogo

Após a corrida terminar, é preciso comunicar aos outros personagens que a corrida acabou e recomeçar o jogo para que possamos jogar novamente.

__O objeto vencedor deve anunciar para todos que ele ganhou.__

1. Clique sobre o papagaio.
Adicione um bloco que anuncia "terminou" após o ele dizer que ganhou.



		quando a tecla [a ] for pressionada
			se <[correndo v]= (1) >
			mova (4) passos
			se <tocando em [borda v]?>
				mude [correndo v] para (0)
				toque o som [gravação1]
				diga [O papagaio ganhou!] por (3) segundos 
				anuncie [terminou] para todos
			fim
		fim

2. Agora precisamos adicionar o código para ouvir a mensagem, e também mover o papagaio de volta para a posição inicial.
O que acontece se você mudar o valor de x?



		quando eu ouvir [terminou]
		mude [x v] para (-175)

3. Agora adicione o mesmo código para o leão. Teste diferentes valores de x para certificar-se que leão e o papagaio estão na linha de largada.
4. Também queremos colocar o leão e o papagaio na mesma posição quando o projeto é executado, 
então adicione os comandos para cada um se mova para o início
quando a bandeira for clicada.



		quando BANDEIRA clicado 
		mude [x v] para (-175)

5. Agora clique no objeto botão e adicione os comandos para que ele reapareça quando ouvir a mensagem __terminou__.

### Teste o projeto
__Clique na bandeira verde.__


Você consegue jogar com um amigo, um correndo com o papagaio pressionando 'A' e o outro
com o Leão pressionando 'L'?

Salve o projeto

##Desafio: Adicionando um turbo

* __Tente adicionar um turbo__ que você pode usar uma vez a cada corrida. Este turbo move o papagaio ou o leão __30 passos de uma só vez.__
* __Adicione um novo traje__ com fogo saindo atrás de cada personagem e faça ele aparecer, quando o turbo é pressionado.
* __Crie outro som__ que o personagem vai fazer quando o turbo é pressionado.


### Teste o projeto

Salve o projeto


__Parabéns você terminou, agora você pode desfrutar do jogo!__

Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ no menu!
