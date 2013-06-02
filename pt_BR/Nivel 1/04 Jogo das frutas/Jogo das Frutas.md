Nível 2 

#Jogo das frutas (caça-níqueis)

__Introdução:__
Este é um jogo que tem três objetos que mudam de traje. Você deve fazer eles pararem mostrando a mesma imagem (como uma máquina caça-níqueis!).

## PASSO 1: Criar um objeto que muda de traje

__Vamos começar importando as imagens do jogo__

1. Crie um novo projeto Scratch. Exclua o gato clicando nele com o botão direito e em Excluir
2. Importe um novo objeto.
3. Escolha uma imagem de qualquer pasta. No nosso caso usamos things/bananas1, mas você pode
usar a imagem que quiser.
4. Clique na aba Trajes e importe mais dois trajes, assim teremos três no total
(Usamos animals/bee1 e things/lego, mas você pode usar qualquer imagens).

__Agora que temos alguns trajes, queremos que o objeto mude entre eles.__

## Passo 2: Fazendo a mudança de imagem

1. Clique na aba Comandos.
2. Clique em Controle e arraste o bloco "quando bandeira clicada" para área de comandos. Este será
acionado quando clicarmos na bandeira verde.
3. Encaixe um sempre logo embaixo.
4. Clique na bandeira verde no canto superior direito. Observe o contorno branco em nosso bloco de comandos. Isso significa que nossos comandos estão sendo executados. E o clique na bandeira verde que desencadeia isso.
5. Agora clique em Aparência e encaixe um bloco __próximo traje__ dentro do __sempre__
6. Como fazer para diminuir a velocidade em que mudamos de image? Clique em Controle e arraste um bloco __espere 1 segundos__
7. Ajuste o tempo de espera (um tempo de 0,1 s parece bom). O que aconteceria se não tivéssemos o bloco espere?

		quando BANDEIRA clicada
		sempre 
			próximo traje
			espere (0.1) segundos
		fim


###Teste o projeto
__Clique na bandeira verde.__ 
As imagens mudam em uma velocidade aceitável?

Salve o projeto

### Coisas para tentar

Ajuste o tempo do bloco __espere__.Quais valores fariam o jogo ficar muito fácil ou muito difícil?

## PASSO 3: Fazer parar quando clicado

Excelente! Nós podemos fazer os trajes do objeto mudarem sem parar, mas como é que vamos fazê-lo parar quando clicar sobre ele?

1. Crie uma nova variável clicando Variáveis ​​e criar uma variável. Dê o nome de __parado__ e deixe marcado a opção para todos os objetos, em seguida, desmarque a caixa ao lado dela para que ele não seja exibida no palco.
2. Mude a variável __parado__ para 1 quando alguém clicar sobre a imagem. Para isso utilize o bloco
__quando Sprite1 clicado__ e o bloco __mude parado para__. 
3. Agora precisamos fazer a imagem parar de mudar quando a variável __parado__ é igual a 1. Clique controle e substitua o bloco __sempre__ por um bloco __sempre se__ e use um novo operador igual (=) para testar se __parado__ é igual a 0
4. Finalmente, encaixe um bloco __mude parado para 1__ logo abaixo do __quando bandeira clicada__

### Teste o projeto
__Clique na bandeira verde, espere por um momento, em seguida, clique sobre o objeto.__ 

Os trajes mudam antes de você clicar? 
Ele para quando você clica sobre ele?
__Clique novamente na bandeira verde__Ele para quando você posiciona o ponteiro do mouse sobre ela, sem clicar? Ele para quando você clica em outro lugar do palco? Em algum outro lugar da janela do Scratch? Em algum lugar fora da janela do Scratch?

Salve seu projeto

## Passo 4: Criando os outros objeto
__Precisamos adicionar outros objetos para que possamos fazer o nosso jogo!__

1. Duplique o objeto 1 (sprite1) clicando com o botão direito sobre ele, no canto inferior direito.
2. Duplique-o novamente para termos três objetos na tela.
3. Posicione os objetos para que eles fiquem em linha. Redimensione eles se necessário.

### Teste o projeto
__Clique na bandeira verde.__ Todos os objetos deve mudar de traje. Tente fazê-los parar na mesma imagem!

Salve seu projeto

### Coisas para tentar

No Início todos os objetos mostram o mesmo traje ao mesmo tempo. Que tal você fazer os objetos mudarem para um traje aleatório quando a bandeira verde for clicado?
Dica: tente escolher um traje aleatório para cada objeto quando o jogo é iniciado.

__Parabéns você terminou o jogo básico. Há mais coisas que você pode fazer para o seu jogo. Dê uma olhada nestes desafios!__


## Desafio 1: Aumente a dificuldade do jogo

Mude a dificuldade do jogo de alguma maneira. Apenas fazer os imagens mudarem mais rápido é muito fácil. Tente fazer algo mais criativo. Algumas idéias que você pode experimentar:

1. Alterar o número de trajes de cada objeto.
2. Faça com que alguns objetos tenham trajes únicos.
3. Faça com que o tempo entre as mudanças de traje seja diferente.
4. Faça com que cada objeto mude para um traje aleatório e não para o próximo traje. 

__Divirta-se com as suas próprias idéias!__

Toda vez que você faz uma alteração, pense se o o jogo ficou mais fácil ou mais difícil. O jogo é muito fácil ou muito difícil? Como você pode ajustar a dificuldade para que fique melhor?


## Desafio 2: Faça o jogo fica mais difícil e mais fácil ao longo do tempo

Diferentes pessoas têm diferentes habilidades em jogar o jogo. __Como você poderia fazer o jogo ajustar sua dificuldade, dependendo do jogador?__

Uma maneira que você pode fazê-lo é __ajustar a velocidade da mudança de trajes__. Você pode criar uma variável chamada __intervalo__, para dar a duração do bloco espere de cada objeto. Se o jogador ganha a rodada, a variável intervalo pode ser reduzido um pouco (para tornar o jogo mais difícil). Se o jogador perde a rodada, o atraso pode ser aumentado um pouco (para tornar o jogo mais fácil).

## Desafio 3: Detectar quando todos os sprites pararem no mesmo traje

__O Objetivo do jogo é clicar sobre os objetos para que eles pararem mostrando o mesmo traje. Seria bom se o palco detectasse quando você terminar de jogar e, em seguida, diga se você ganhou ou perdeu, verificando se cada objeto tem o mesmo traje.__

Em primeiro lugar, a palco precisa saber quando o jogador tiver acabado. Para fazer isso o palco deve verificar se todos os objetos pararam de se mover cada vez que eu clico em um deles. Modifique o bloco __quando clicado__ de cada objeto para que ele anuncie uma nova mensagem, por exemplo verificaFim.

O palco pode receber esta mensagem e verificar se o jogo acabou verificando se as variáveis __parado__ dos três objetos valem 1. Para isso, encaixe um bloco __posição x de__ e mude "posição x" para "parado". Se a variável __parado__ dos três tem valor de 1, sabemos que o jogo acabou e nós podemos verificar se o jogador ganhou.

Para fazer isso, podemos usar a mesma tipo de bloco __posição x de__, mas em vez de olhar a variável __parado__, iremos olhar a variável traje# e assim podemos comparar se Sprite1 tem o mesmo traje que Sprite2, e se Sprite2 tem o mesmo traje que Sprite3.

Para fazer isso, você precisa de um bloco __se__ para verificar cada variável, e dentro dele um bloco __se ... senão__ para ver se o jogador ganhou ou perdeu, comparando cada 
traje

Deste ponto em diante, você pode anunciar o resultado do jogo usando um bloco __anuncie__ e receber esta mensagem em um outro objeto. Que tal fazer o Felix aparecer para felicitar o jogador?


__Parabéns você terminou, agora você pode desfrutar do jogo!__
Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ no menu!
