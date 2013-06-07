Nível 1

#Félix & Herbert

__Introdução:__
Vamos criar um jogo de pega-pega com o gato Félix e o rato Herbert. Você controla o Herbert com o mouse e tenta fugir do gato Félix. Quanto mais tempo você ficar sem ser pego, mais pontos você ganha. Cuidado, se você for pego, você perderá pontos!

##PASSO 1: Félix segue o mouse
Acompanhe o seu progresso marcando os quadros abaixo.

1. Crie um projeto novo.
2. Dê um duplo clique no fundo branco atraz do gato. Em seguida, na aba __Fundos de Tela__, clique em __Importar__ e escolha o fundo indoors/hall.
3. Clique no Félix e mude o nome de objeto1 para Félix. 
4. Certifique-se que o modo de rotação do Félix é somente esquerda-direita.
5. Crie estes comandos:


		quando BANDEIRA clicado
			sempre
			aponte para [ponteiro do mouse v]
			mova (10) passos
			próximo traje
			toque o tambor (62) por (0.3) batidas
		fim

		
###Teste o projeto
__Clique na bandeira verde.__
O Félix esta seguindo o ponteiro do mouse? Ele parece andar enquanto se movimenta? A velocidade que ele se move é correta?

Salve o projeto

##PASSO 2: Félix persegue o Herbert

__Agora vamos fazer com que o Félix persiga o Herbert, ao invés de perseguir o mouse.__

1. Crie um novo personagem, clicando em "Escolha um sprite do arquivo" e escolha Animals/mouse1
2. Mude o nome do personagem para Herbert
3. Certifique-se de que o modo de rotação do Herbert é somente esquerda-direita.
4. Clique em __Trajes__ e __Editar__ e diminua o tamanho do Herbert clicando 6x no botão encolher.
5. Crie os comandos seguintes no Herbert (Certifique-se de que os comandos são criados para o Herbert, clicando 2x sobre ele antes de começar a encaixar os blocos): 

		quando BANDEIRA clicado
		sempre
			vá para [ponteiro do mouse v]
			aponte para [Felix v]		
		fim

###Teste o projeto
__Clique na bandeira verde.__

O Herbert se move com o ponteiro do mouse? O Félix está perseguindo o Herbert?

Salve o projeto

##STEP 3: Félix avisa quando ele pegar o Herbert

__Vamos fazer com que o Félix nos diga quando ele pegou o Herbert__


1. Mude os comandos do Félix para que eles fiquem assim:

		quando BANDEIRA clicado
		sempre
		aponte para [ponteiro do mouse v]
		mova (10) passos
		próximo traje
		toque o tambor (62) por (0.3) batidas
		se <tocando em [Herbert v]>
				diga [Te peguei!] por (1) segundos
			fim
		fim

###Teste o projeto
__Clique na bandeira verde.__

O Félix diz quando pega o Herbert?

Salve o projeto.

##PASSO 4: Herbert vira fantasma quando pego

__Ao invés de dizer algo, nós vamos fazer com que Herbert vire um fantasma quando for pego.__

1. Modifique os comandos do Félix para enviar uma mensagem quando ele pegar o Herbert.

		quando BANDEIRA clicado
		sempre
			aponte para [ponteiro do mouse v]
			mova (10) passos
			próximo traje
			toque o tambor (62) por (0.3) batidas
			se <tocando em [Herbert v]>
				anuncie [pego v] para todos
				toque o tambor (58) por (0.2) batidas
				espere (1) segundos
			end
		end


2. Clique sobre o Herbert, vá até a aba trajes, clique em importar e escolha o traje fantasy/ghost2-a.
3. Edite o traje para ele ficar menor.
4. Mude o nome dos trajes do Herbert, de maneira que o rato (mouse1) se chame 'vivo' e o fantasma (ghost2-a)  se chame 'morto'.
5. Crie novos comandos para o Herbert, que irão transformá-lo em um fantasma.

		quando eu ouvir [pego v]
		mude para o traje [morto v]
		espere (0.5) segundos
		mude para o traje [vivp v]	
	
	
###Teste o projeto

__Clique na bandeira verde.__

O Herbert se transforma em fantasma quando pego?

O Félix toca o som certo no momento certo?

O Félix fica parado tempo suficiente para o Herbert fugir?

Salve o projeto

##PASSO 5: Conte os pontos

__Vamos criar um placar para saber se estamos indo bem. O placar começa do zero, e aumenta um ponto a cada segundo. Quando o Félix pegar o Herbert, o jogador perderá cem pontos.__

1. Clique em __Variáveis__ e Crie uma Variável chamada placar.  Mantenha selecionada a opção "para todos os projetos".
2. Clique no placar e crie estes dois blocos de comandos.

		quando BANDEIRA clicado
		mude [placar v] para (0)
		sempre
			mude [placar v] por (1)
			espere (1) segundos
		end
		
		quando eu ouvir [pego v]
		mude [placar v] por (-100)
	

###Teste o projeto
__Clique na bandeira verde.__

Os pontos aumentam um a um a cada segundo?

Os pontos diminuem de 100 quando o Herbert é pego?

O que acontece quando o Herbert é pego antes que o placar chegue a 100?

O placar volta a zero quando você começa um novo jogo?

Salve o projeto

__Parabéns, você acaba de criar o seu primeiro jogo!__
