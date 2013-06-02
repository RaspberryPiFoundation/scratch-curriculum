Nível 3

#Adivinhe o que é!

__Introdução:__
Um objeto aleatório é mostrado na tela, completamente distorcido. Você tem que adivinhar o que e clicar na imagem correspondente. Quanto mais rápido você adivinhar, maior será sua pontuação!

##Passo 1: Faça coisas diferentes aparecem na tela

Valos fazer algumas imagens diferentes aparecer na tela.

1. Inicie um novo projeto Scratch e apagar o personagem do gato.
2. Clique Palco e, em seguida, na aba Fundos de Tela. Importe o fundo de tela __indoors/chalkboard__.
3. Importe um novo personagem e escolha o traje que você quiser. Você pode escolher alguns da pasta __things__ (coisas).
4. Posicione o novo personagem no meio da tela. Se necessário mude o seu tamanho.
5. Clique na aba Trajes e importe mais quatro images. Eles podem ser o que você quiser!
Vamos agora fazer uma imagem aleatória aparecer.
6. Crie estes códigos:



		quando BANDEIRA clicado
		repita (sorteie número entre (1) e (5))
			próximo traje
		fim


###Teste o projeto
__Clique na bandeira verde.__

O personagem mostrar um traje diferente?

__Click Sobre ele mais algumas vezes.__
Você vê trajes diferentes a cada vez? Às vezes você vai obter o mesmo traje duas vezes seguidas, mas isso nao é um problema. Você também pode ter percebido que o personagem treme quando e muda de traje. Nós vamos corrigir isso na próxima etapa.

Salve seu projeto

##Passo 2: Faça com que as imagens fiquem distorcidas

__Agora é hora de fazer uma imagem ficar distorcida, e tornar-se cada ves mais nítida com o passar do tempo. mais clara durante alguns segundos.__

Vamos usar uma variável de contagem para controlar a quantidade de distorção que existe. Se o valor é alto, haverá muita distorção. Na medida que o valor diminui, teremos cada vez menos distorção. A pontuação também atua como um contador de tempo.

1. Na aba __variáveis__, crie uma variável chamada Pontos.

2. Altere os comandos para que eles fiquem assim:



		quando BANDEIRA clicado
		desapareça
		repita (sorteie número entre (1) e (5))
			próximo traje
		fim
		mude [ pontos v] para (110)
		repita até <(score) = (0) >
			mude [pontos v] por (-10)
			mude o efeito [pixelar v] para (pontos)
			mude o efeito [cor v] para (pontos)
			apareça
			espere (1) segundos
		fim


Os novos blocos a inserir são o __desapareça__ bem encima e também todos os blocos abaixo de mude [pontos] para 110.

### Teste o projeto
__Clique na bandeira verde.__

Uma imagem aleatória e distorcida aparece?

A distorção diminui as poucos?

O pontos diminuem à medida que a imagem torna-se menos distorcida?

Você obterém uma imagem sem distorções quando os pontos chegam a zero?

Você ainda obtém uma imagem diferente a cada vez que clica na bandeira verde?

Salve o projeto

### Coisas para tentar

__Modifique a pontuação inicial e também a quantidade em que ele diminui a cada passo.__Como isso muda a forma como a imagem aparece? Isso torna mais difícil ou mais fácil de detectar qual é a imagem?

__Experimente outros efeitos gráficos da lista.__Eles mudam a dificuldade do jogo?

## Passo 3: Permitir que o jogador adivinhar a imagem

Até agora, nós temos uma imagem aleatória aparecendo lentamente, e uma pontuação que diminui ao longo do tempo, mas como fazer para ganhar o jogo? Vamos adicionar algunas objetos na parte inferior da tela para que o jogador clicque. Se o jogador clicar na imagem certa, ele ganha o jogo. Se clicar na imagem errada a imagem desaparece e o jogo continua.

Primeiro, precisamos saber qual é a resposta certa.

1. Crie uma nova variável chamada __resposta__. Certifique-se que a opção para todos os objetos está clicada.
2. Mude os comandos que você criou para gravar a resposta certa. Adicione o bloco mude [resposta] para [traje #] logo após o primeiro repita:



		quando BANDEIRA clicado
		desapareça
		repita (sorteie número entre (1) e (5))
			próximo traje
		fim
		mude [resposta] para (traje #)
		mude [ pontos v] para (110)
		repita até <(score) = (0) >
			mude [pontos v] por (-10)
			mude o efeito [pixelar v] para (pontos)
			mude o efeito [cor v] para (pontos)
			apareça
			espere (1) segundos
		fim

__Agora vamos criar os objetos para que o jogador possa clicar.__

3. Duplique o objeto principal e arraste a cópiar para o canto inferior esquerdo dor palco.
4. Renomeie esse objeto para __resposta1__. (Isso faz com que seja mais fácil de se referir a ele.)
5. Apague todos os comandos de __resposta1__ e todos os seus trajes, exceto o primeiro.
6. Repita estas três últimas etapas colocando a __resposta2__ ao lado da __resposta1__ e apague tudo, exceto o segundo traje.
7. Repita isso mais três vezes para a __resposta3__, __resposta4__ e __resposta5__.
Você deve acabar com uma fileira de cinco objetos resposta no balco, cada uma exibindo uma imagem correspondente a uma resposta possível. __Nenhum dos objetos resposta pode ter comandos dentro dele!__

Agora, vamos fazer com que cada objeto reaja au clique dependendo se a resposta é correta ou não.

8. Adicionar este script para o objeto resposta1:



		quando resposta1 clicado
		se <(resposta) = (1)>
			anuncie [ganhou v] para todos
		senão
			desapareça
		fim


9 Arraste estes comandos para cada um dos outros objetos resposta. __Em cada objeto, substitua o 1 por 2, 3, e assim por diante.__
10. Agora temos de acrescentar algo que ouça a mensagem ganhou. Volte para objeto1, o que aparece na tela. E adicione este script:



		quando eu ouvir [ganhou v]
		diga (junte [Parabéns! Sua pontuação é de ] [pontos])


###Teste o projeto
__Clique na bandeira verde.__



O que acontece quando você clica na __resposta certa__?

O que acontece quando você clica na resposta __errada__?

O que acontece com a resposta errada quando você __começa um novo jogo__?

O teste revela dois problemas. Primeiro, respostas erradas não reaparecer quando o próximo jogo começar. Em segundo lugar, o placar não parar de diminuir quando encontramos a resposta certa.

11. Para resolver o primeiro problema, adicione estes comandos para cada um dos cinco objetos de resposta:



		quando BANDEIRA clicado
		apareça


Para resolver o segundo problema, temos de parar o bloco repita do __objeto 1__ pare que ele pare quando o jogador clica na resposta certa. Vamos usar uma nova variável para fazer isso. Ela será inicializada a __zero__ quando o jogo começa e será mudada para __um__ quando o jogador ganhar. Nós vamos fazer com que o laço de repetiça __repita até__ pare quando os __pontos__ atingem __zero__ OU a variavel que sinaliza o fim do jogo valha __um__.

12. Crie uma nova variável chamada "ganhou?"
13. Alterar os comandos para que eles fiquem assim:



		quando BANDEIRA clicado
		desapareça
		repita (sorteie número entre (1) e (5))
			próximo traje
		fim
		mude [resposta] para (traje #)
		mude [ pontos v] para (110)
		mude [ganhou?] para (0)
		repita até < ( (score) = (0 ) ) ou ( (ganhou?)= (1) ) >
			mude [pontos v] por (-10)
			mude o efeito [pixelar v] para (pontos)
			mude o efeito [cor v] para (pontos)
			apareça
			espere (1) segundos
		fim

		Quando eu ouvir [ganhou v]
		mude [ganhou?] para (1)
		limpe os efeitos gráficos
		diga (junte [Parabéns! Sua pontuação é de ] [pontos])


Salve o projeto

__Parabéns você terminou o jogo básico.__

Há mais coisas que você pode fazer para o seu jogo. Dê uma olhada nestes desafios!


##Desafio 1: Faça o jogo mais difícil ou mais fácil

Alterar a dificuldade do jogo.

* Tente mudar o quão rápido a imagem é revelada e quão rápido a pontuação diminui.
* Altere o tipo de distorções na imagem.
* Substitua as imagens a serem adivinhadas, para torná-los mais semelhantes ou mais diferentes. Se você fizer isso, não se esqueça de alterar o traje no objeto de resposta.


Salve o projeto


##Desafio 2: Distorcer a imagem de forma diferente em cada rodada

Neste momento, cada rodada do jogo usa a mesma distorção. Na Etapa 2, você pode ter tentado algumas distorções diferentes que funcionam tão bem quanto cor e pixelizão.

Encontre algumas distorções diferentes que funcionam bem.

Mudar o jogo para que cada rodada usa uma distorção diferente dentro do bloco repita até.

__Dica:__ Tente criar uma nova variável, chamada distorção. Faça com que ela tenha um valor aleatório no início do jogo. Use blocos __se__ dentro do laço repita até para aplicar a distorção desejada para a rodada.

Salve o projeto

## Desafio 3: Faça um jogo com várias rodadas

Até então, cada rodada é independente. Modifique o jogo para que possamos ter várias rodadas. Por exemplo, um jogo de três rounds, então o jogador tem que adivinhar três imagens e pode marcar até 300 pontos.

__Dica:__ Você vai precisar de uma variável extra para armazenar o total geral em todos os rodadas. Você também vai precisar de um laço __repita__ para os diferentes rodadas.

__Dica:__ Você também terá que fazer com que as respostas erradas reapareçam no início de cada rodada. Talvez você possa usar uma mensagem __anuncie para todos__ para fazer isso?

Salve o projeto


## Desafio 4: Faça as rodadas finais mais difíceis

À medida que você passar por diferentes rodadas, torne o jogo cada vez mais difícil.

Cada rodada deve valer a mesma quantidade de pontos? Você deve ganhar mais pontos se você responder rápido nas rodadas finais que são mais difíceis?

__Dica:__ Como fazer qual é a rodada atual? Como você pode usar isso para mudar a dificuldade e a pontuação?

Salve o projeto


##Desafio 5: Continue o jogo até que o jogador erre

Em vez de usar um número fixo de rodadas, continue o jogo até que o jogador não consiga acertar uma imagem. Isso provavelmente só funciona se o jogo fica mais difícil em rodadas posteriores.

Salve o projeto

## Desafio 6: Faça o jogo mais difícil ou mais fácil dependendo de quão bom o jogador é

Ao invés de sempre fazer o jogo mais difícil, faça o jogo ajustar a dificuldade dependendo da habilidade do jogador. Se eles acerta a imagem rapidamente, faça com que a próxima rodada seja um pouco mais difícil. Se ele errar a imagem, ou demorar para encontrar a resposta faça a próxima próxima um pouco mais fácil.

Essa idéia só tem sentido se você não somar a pontuação de alguém ao longo de várias rodadas.

Salve o projeto

## Desafio 7: Acompanhe a maior pontuação

Acompanhe a maior pontuação. Se alguém consegue vencê-lo, pergunte o seu nome e atualizar a pontuação mais alta. Certifique-se que a maior pontuação, e o nome da pessoa que marcou ele, sejam exibidos.


Salve o projeto


##Desafio 8: Fazer com que erros custem pontos

No momento, não há nenhuma penalidade se você clicar em todas as respostas o mais rápido possível. Mude o jogo para que a pontuação total diminua cada vez que uma resposta errada seja dada.

Isso faz com que o jogo fique melhor?


Salve o projeto


__Parabéns você terminou, agora você pode desfrutar do jogo!__

Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ no menu!
