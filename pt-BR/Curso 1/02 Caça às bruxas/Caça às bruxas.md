---
layout: scratchProject
---
Nível 1

#Caça às bruxas

__Introdução:__
Neste jogo você deve caçar as bruxas que aparecem na tela. Você ganha pontos que acertar uma delas. 
O objetivo é ganhar o máximo de pontos em 30 segundos!

##PASSO 1: Crie uma bruxa voadora

1. Crie um novo projeto Scratch.
2. Apague o personagem do gato e substitua a imagem de fundo pela imagem nature/woods.
3. Use o botão _escolha um sprite do arquivo_ para adicionar um novo personagem bruxa ao projeto (selecione fantasy/witch1). 

Agora queremos que a nossa bruxa se mova

4. Adicione uma variável chamada "velocidade" e selecione a opção __para este objeto apenas__.

__Importante:__ No Palco, deve aparecer “objeto1 velocidade”.
Se aparecer apenas “velocidade”, apague a variável e crie de novo selecionando "para este objeto apenas".
Desmarque a caixa ao lado do bloco velocidade no quadro de variáveis para que ela não apareça no Palco.
Nós usaremos esta variável para poder mudar a velocidade da bruxa durante o jogo.

Nós queremos que a bruxa comece a se mexer quando o jogo iniciar, então crie estes comandos:

		quando BANDEIRA clicado
		mude [velocidade v] para (5)
		sempre
			mova(velocidade) passos
		fim
		
###Teste o projeto
__Clique na bandeira verde__ e olhe o que a bruxa faz. 

Por que ela fica trancada no canto da tela ?

6. Para não ficar trancada a bruxa deve dar meia volta quando tocar na borda do palco. 
Abaixo do comando __mova__, adicione um  comando `se tocar na borda, volta`.

		quando BANDEIRA clicado
		mude [velocidade v] para (5)
		sempre
			mova(velocidade) passos
			se tocar na borda, volta
		fim
		
7. Para evitar que a bruxa fique de cabeça para baixo, clique  __somente esquerda-direita__ na área de propriedades do personagem.

###Teste o projeto

__Clique na bandeira verde.__ 

A bruxa se move de um lado par a outro atravessando a tela?

Salve o projeto

###Sugestões

__Tente mudar o valor da variável velocidade para a bruxa voar mais rápido ou mais devagar.__

__Como você faria a bruxa acelerar com o passar do tempo?__
(Esta é uma pergunta difícil, mas não se preocupe se você não sabe como fazer. Você terá mais dicas enquanto você trabalha neste projeto.)

##PASSO 2: Faça a bruxa aparecer e desaparecer de maneira aleatória

Para tornar o jogo mais divertido, vamos fazer as bruxas aparecerem e desaparecerem aleatoriamente. 
Faremos isso com um outro conjunto de comandos que é executado ao mesmo tempo que os comandos que fazem a bruxa se mexer.
Estes novos comandos vão esconder a bruxa por um tempo aleatório e em seguida a bruxa vai aparecer, também por um tempo aleatório. 
Esta operação é repetida para sempre (ou até que o jogo acabe).

Crie estes comandos para a bruxa:

		quando BANDEIRA clicado
		sempre
			desapareça
			espere (sorteie número entre (2) e (5)) segundos
			apareça
			espere (sorteie número entre (3) e (5)) segundos
		fim

###Teste o projeto

__Clique na bandeira verde.__ 

A bruxa se mexe de um lado para o outro atravessando a tela, desaparecendo e aparecendo aleatoriamente?

Salve o seu projeto

###Sugestões

__Tente mudar os valores entre os quais os números são sorteados. 
O que acontece se você escolher números muito grandes ou muito pequenos?__
(Isto dá pistas sobre como fazer a bruxa acelerar de acordo com a duração do jogo?)

##PASSO 3: Faça a bruxa desaparecer ao é clicada

Para transformar isso em um jogo, precisamos que o jogador faça algo. Eles precisam clicar na bruxa para que ela desapareça. 
Ao ser clicada, a bruxa deve desaparecer e também vamos aproveitar para toca um som, assim o jogo ficará mais divertido!

1. Na aba de Sons, importe o som electronic/fairydust. 
2. Adicione estes comandos para a bruxa:

		quando objeto1 clicado
		desapareça
		toque o som [Fairydust v]
		
###Teste o projeto

__Clique na bandeira verde.__

A bruxa desaparece e toca um som quando clicada?

Salve o projeto

##Passo 4: Adicione um placar e um cronômetro

Tudo bem, nós temos uma bruxa que voa pela tela, mas o que nós queremos fazer é um jogo! 
Além de fazer a bruxa desaparecer vamos também marcar pontos cada vez que clicamos na bruxa.  
Mas não é só isso, também vamos inserir um limite de tempo para a partida. 

Para fazer um placar e o um cronômetro nós podemos usar variáveis.

1. Crie uma nova variável __para todos os objetos__ chamada placar, 
e modifique os comandos da bruxa para somar um a esta variável cada vez que clicarmos em uma bruxa.


		quando objeto1 clicado
		desapareça
		toque o som [Fairydust v]
		mude [placar v] por (1)

	
2. Vá para o Palco e crie uma nova variável (dessa vez somente para o palco, usando a opção __para	este objeto apenas__) e dê o nome de tempo. 
Adicione novos comandos que serão executado quando a bandeira verde for clicada. 
Estes comandos servem para mudar o tempo para 30 e zerar o placar. 
Em seguida use um comando __repita até__ para esperar um segundo e diminuir o tempo de um. Isto deve ser repetido até que o tempo seja 0. 

Quando o tempo chegar a zero, devemos usar um comando __pare tudo__ para interromper a partida.
	
		quando BANDEIRA clicado
		mude [cronômetro v] para (30)
		mude [placar v] para (0)
		repita até <[cronômetro] = [0]>
			espere (1) segundos
			mude [cronômetro] por (-1)
		fim
		pare tudo

###Teste o projeto

__Clique na bandeira verde.__

Salve o seu projeto


###Sugestões
__Como você faria para acelerar a bruxa durante a partida?__


__Parabéns, você terminou o jogo básico. Existem mais coisas que você pode fazer. Tente este desafio!__

##Desafio: Adicione mais bruxas

Se uma bruxa é bom, várias bruxas deve ser ainda mais legal! Então, vamos criar três bruxa voando pela tela.

1. Duplique a bruxa fazendo clicando com o botão direito sobre ela, na lista de personagens em baixo à direita da tela.
2. Para cada bruxa ajuste o tamanho do personagem para que cada uma delas tenha um tamanho diferente.
3. Para cada bruxa mude a variável velocidade para que cada uma voe com velocidade diferente das outras.
4. Distribua as bruxas pelo palco para que elas não fiquem todas juntas.

###Teste o projeto
__Clique na bandeira verde.__

Você vê três bruxas que se movem de um lado a outro da tela, 
que aparecem e desaparecem aleatoriamente, e que desaparecem quando você clica nelas?

Salve o seu projeto


###Sugestões
1. Qual a quantidade adequada de bruxas para o jogo ?
2. Você pode fazer as bruxas terem aparências diferentes? 
Você poderia editar seus trajes, ou usar alguns comandos da aba _Aparência_ para mudá-las.
3. Você pode fazer o número de pontos ganhos para cada bruxa ser diferente? Que tal fazer a bruxa mais veloz (e menor) valer 10 pontos?

__Parabéns, você terminou, agora aproveite!__

Não esqueça que você pode compartilhar seu jogo com todos os seus amigos e família clicando em __Compartilhar__ na barra de menu!
