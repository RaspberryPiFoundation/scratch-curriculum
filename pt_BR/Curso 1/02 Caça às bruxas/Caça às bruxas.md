Nível 1

#Caça às bruxas

__Introdução:__
Você ganha pontos acertando as bruxas que aparecem na tela. O objetivo é ganhar o máximo de pontos em 30 segundos!

##PASSO 1: Crie uma bruxa voadora

1. Crie um novo projeto scratch.
2. Apague o personagem do gato e substitua a imagem de fundo com a imagem nature/woods.
3. Use o botão "Escolha um sprite do arquivo" para adicionar ao projeto um novo personagem de bruxa (selecione fantasy/witch1). 

Agora queremos que a nossa bruxa se mexa

4. Adicione uma variável chamada "velocidade" e selecione a opção __para este objeto apenas__.
__Importante:__ No Palco, deve aparecer “objeto1 velocidade”.
Se aparecer apenas “velocidade”, apague a variável e crie-a de novo selecionando "para este objeto apenas".
Desmarque a caixa ao lado do bloco velocidade no quadro de variáveis de modo que ela não apareça no Palco.
 Nós usaremos esta variável para que possamos mudar a velocidade com que a bruxa se mexe durante o jogo.
5. Nós queremos que a bruxa comece a se mexer quando o jogo comece, então crie estes blocos de comando:

		quando BANDEIRA clicado
		mude [velocidade v] para (5)
		sempre
			mova(velocidade) passos
		fim
		
###Teste o projeto
__Clique na bandeira verde__ e olhe o que a bruxa faz. Por que ela fica trancada no canto da tela ?

6. Para evitar que a bruxa fique trancada nós precisamos fazê-la ir para o outro lado quando ela atinge o canto da tela. Abaixo do bloco __mova__, adicione um  bloco __se tocar na borda, volta__.

		quando BANDEIRA clicado
		mude [velocidade v] para (5)
		sempre
			mova(velocidade) passos
			se tocar na borda, volta
		fim
		
7. Para evitar que a bruxa fique de cabeça para baixo, clique  __somente esquerda-direita__ na área de propriedades do personagem.

###Teste o projeto
__Clique na bandeira verde.__ 
A bruxa se mexe de um lado a outro atravessando a tela?

Salve o projeto

###Sugestões
__Tente mudar o valor da variável velocidade para fazê-la voar mais rápido ou mais lentamente.__

__Como você faria a bruxa acelerar com o passar do tempo?__
(Esta é uma pergunta difícil, mas não se preocupe se você não sabe como fazê-lo. Você terá mais dicas enquanto você trabalha neste projeto.)

##PASSO 2: Faça a bruxa aparecer e desaparecer de maneira aleatória

Para tornar o jogo mais divertido, nós queremos que a bruxa apareça e desapareça de modo aleatório. Faremos isso com um outro bloco de comandos que é executado ao mesmo tempo que os comandos que fazem a bruxa se mexer. Este novo bloco precisa esconder a bruxa durante um tempo aleatório, então fazê-la aparecer durante um tempo aleatório, e repetir isso para sempre (ou até que o jogo acabe).

Crie este script para a bruxa:


		quando BANDEIRA clicado
		sempre
			desapareça
			espere (sorteie número entre (2) e (5)) segundos
			apareça
			espere (sorteie número entre (3) e (5)) segundos
		fim

###Teste o seu projeto
__Clique na bandeira verde.__ 
A bruxa se mexe de um lado para o outro atravessando a tela, desaparecendo e aparecendo aleatoriamente ?

Salve o seu projeto

###Sugestões
__Tente mudar os valores aleatórios. O que acontece se você escolher números muito grandes ou muito pequenos ?__
(Isto dá pistas sobre como fazer a bruxa acelerar mais de acordo com a duração do jogo?)

##PASSO 3: Faça a bruxa desaparecer quando ela é clicada

Para transformar isso em um jogo, precisamos que o jogador faça algo. Eles precisam clicar na bruxa para que ela desapareça. Quando a bruxa é clicada queremos que ela desapareça e que seja tocado um som.

1. Na aba de Sons, importe o som electronic/fairydust. 

2. Adicione estes comandos para a bruxa:


		quando objeto1 clicado
		desapareça
		toque o som [Fairydust v]
		
###Teste o seu projeto
__Clique na bandeira verde.__

A bruxa desaparece e toca um som quando é clicada ?

Salve o projeto

##Passo 4: Adicione um placar e um cronômetro

Nós temos uma bruxa, mas agora nós queremos fazer um jogo! Nós queremos marcar pontos a cada vez que clicamos na bruxa mas também queremos ter um limite de tempo para a partida. Nós podemos usar uma variável para o placar
 e para o cronômetro.


1. Crie uma nova variável __para todos os objetos__ chamada placar, e modifique os comandos da bruxa para incrementar esta variável de um quando ela é clicada.


		quando objeto1 clicado
		desapareça
		toque o som [Fairydust v]
		mude [placar v] por (1)

	
2. Vá para o Palco e crie uma nova variável (dessa vez somente para o palco, usando a opção __para	este objeto apenas__) chamada cronômetro. Adicione novos comandos que serão executado quando a bandeira verde é clicada para definir o cronômetro para 30 e para reinicializar o placar a 0. Então use um bloco 'repita até" para esperar um segundo e então diminui o cronômetro de um. Isto deve repetir até que o cronômetro seja 0, momento em que se deve usar __pare tudo__ para interromper a partida.
	
		quando BANDEIRA clicado
		mude [cronômetro v] para (30)
		mude [placar v] para (0)
		repita até <[cronômetro] = [0]>
			espere (1) segundos
			mude [cronômetro] por (-1)
		fim
		pare tudo

###Teste o seu projeto
__Clique na bandeira verde.__

Salve o seu projeto


###Sugestões
__Como você faria para acelerar a bruxa durante o andamento da partida?__


__Parabéns, você terminou o jogo básico. Porém existem mais coisas que você pode fazer com o seu jogo. Tente este desafio!__

##Desafio: Adicione mais bruxas

Se uma bruxa é bom, mais bruxas deve ser melhor! Vamos ter três bruxa voando pela tela.

1. Duplique a bruxa fazendo um clique direito nela na lista de personagens.
2. Para cada bruxa ajuste o tamanho do personagem para que as bruxas tenham tamanhos diferentes.
3. Para cada bruxa mude a variável velocidade para que eleas voem com velocidades diferentes.
4. Mova as bruxas pelo painel para que elas nao fiquem todas juntas.

###Teste o seu projeto
__Clique na bandeira verde.__

Você tem três bruxas que se movem de um lado a outro da tela, que aparecem e desaparecem aleatóriamente, e que desaparecem quando voce clica nelas?

Salve o seu projeto


###Sugestões
1. Qual a quantidade adequada de bruxas para o jogo ?
2. Voce pode fazer as bruxas tenham aparências diferentes? Voce poderia editar suas fantasias, o usar alguns blocos da aba _Aparência_ para mudá-las.
3. Você pode fazer com o número de pontos ganhos por cada bruxa seja diferente? Que tal fazer com que a bruxa mais veloz (e menor) valha 10 pontos?


__Parabéns voce terminou, agora aproveite o jogo !__
Não se esqueça que voce pode compartilhar seu jogo com todos os seus amigos e família clicando em __Compartilhar__ na barra de menu!
