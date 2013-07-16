Nível 3

# Ferramenta de desenho

__Introdução:__
Neste projeto, vamos criar uma ferramenta de pintura para criar desenhos.
Esta ferramenta permitirá escolher a cor do lápis, limpar a tela, usar carimbos e muito mais!

## PASSO 1: Arrastando e desenhando

Vamos começar com um lápis que risca quando arrastado sobre a tela.

1. Crie um novo projeto Scratch. Apague o gato clicando com o botão direito e em __apagar__.
2. Clique em __Palco__ e, em seguida, na aba __Fundos de tela__ importe o fundo __indoors/chalkboard__.
3. Criar um novo objeto chamado __lápis__, utilizando __recursos/lápis-verde.__
4. Vá para a aba __Trajes__, clique em Editar e faça com que o centro da imagem fique na ponta da caneta. 
Para isso, clique em __selecionar centro do traje__ (no canto em baixo à esquerda), 
e arraste as linhas até que elas estejam na ponta do lápis.
5. Faça a caneta seguir o mouse usando um bloco __sempre__ e um bloco __vá para [ponteiro do mouse]__


		quando BANDEIRA clicado
		sempre
			vá para [ponteiro do mouse v]
		fim


__Vamos fazer com que o objeto lápis se comporte como um lápis de verdade.__ 
Dê uma olhada na aba caneta e você encontrará vários blocos relacionados à pintura. 
Por enquanto os blocos que nos interessam são __abaixe a caneta__ e __levante a caneta__

6. Vamos usar o botão do mouse para controlar o lápis - sempre que o mouse estiver pressionado 
nós vamos __abaixar a caneta__, e quando o botão do mouse estiver solto nós vamos __levantar a caneta__. 
Para isso, utilize o bloco __se ... senão__ e o bloco __mouse pressionado?__ .


		quando BANDEIRA clicado
		sempre
			vá para [ponteiro do mouse v]
			se <mouse pressionado?>
				abaixe a caneta
				senão
				levante a caneta
			fim
		fim

### Teste o projeto

__Clique na bandeira verde.__
O lápis segue o mouse? O que acontece se você segurar o botão do mouse pressionado e mover? 
Não se preocupe com a cor do lápis para enquanto.


7. Vai chegar uma hora que a tela vai ficar cheia de rabiscos. Você pode usar o bloco __limpe__ para limpar a tela.


		quando BANDEIRA clicado
		limpe
		sempre
			vá para [ponteiro do mouse v]
			se <mouse pressionado?>
				abaixe a caneta
				senão
				levante a caneta
			fim
		fim


### Teste o projeto
__Clique na bandeira verde.__

Os riscos desaparecem quando você clica na bandeira verde?

Salve o projeto

##PASSO 2: Apagando

Ao invés de ter que reiniciar o projeto para apagar os desenhos, vamos adicionar um botão que cancele o desenho. 
Para fazer isso use o bloco __limpe__.

1. Crie um novo objeto usando __recursos/botão-cancelar__.
2. Altere o nome do objeto para __cancelar__.
3. Posicione o objeto na parte de baixo palco próximo ao canto esquerdo.
4. Crie estes comandos para o objeto __cancelar__:


quando cancelar clicado
limpe


### Teste o projeto
__Clique na bandeira verde.__

O botão cancelar apaga o desenho?

Salve o projeto

## Passo 3: Mudando de cor

Até agora, só desenhamos linhas azuis. Que tal usarmos cores diferentes? 
Vamos adicionar alguns objetos na parte de baixo do quadro. Os objetos serão parecidos com botões coloridos. 
Quando você clicar em um dos botões, ele vai mudar a cor do lápis. O objeto lápis também mudará de cor para sabermos qual cor estamos usando.

1. Adicione um novo objeto, chamado __vermelho__, utilizando __recursos/botão-vermelho__.
2. Ele deve ser posto em algum lugar na parte de baixo do quadro, perto do botão __limpar__.
3. Quando o botão vermelho é clicado, ele deve anunciar a mensagem __vermelho__.


Quando vermelho clicado
anuncie [vermelho v] para todos

__Isso mesmo, são somente dois blocos. A parte complicada fica por conta da lápis.__

No lápis, importe um novo traje, __recursos/lápis-vermelho__. 
Selecione o centro do traje para que ele fique na ponta da caneta, da mesma maneira que você acabou de fazer para traje original.

4. Adicione novos comandos para o lápis. Quando o lápis ouvir a mensagem __vermelho__, 
ele deve mudar para o traje lápis-vermelho e mudar a cor da caneta para vermelho (usando o bloco __mude a cor da caneta para__).

__Dica:__ No bloco __mude a cor da caneta para__ existe um quadrinho colorido, você pode clicar nele e 
usar o conta-gotas para clicar sobre o botão vermelho para garantir que a lápis e o botão tenham a mesma cor.


quando eu ouvir [vermelho v]
mude para o traje

mude a cor da caneta para [#f00]


### Teste o projeto
__Clique na bandeira verde.__

Desenhe uma linha. Em seguida, clique sobre o botão para selecionar a cor vermelha e continue desenhando. 
A lápis muda de traje? Ela desenha em vermelho? O risco sai da ponta da caneta?

Salve o projeto

5. Repita o que você acabou de fazer mas agora usando os botões azul, amarelo e verde.

##Testar o projeto
__Clique na bandeira verde.__

Todos os botões de cor funcionam? Eles mudam o traje do lápis para a cor certa? 
Eles fazem a caneta escrever na cor certa? O desenho sempre sai da ponta do lápis?

Salve o projeto

## Passo 4: Desenhando dentro da margem

Você já deve ter notado que você pode riscar em qualquer lugar do palco, mesmo na margem. 
Nós não queremos que isso aconteça. Queremos manter o desenho no meio do palco. 
Devemos então restringir a posição do lápis para a área de desenho - a parte cinza claro no Palco.


Lembre-se que o Scratch define pontos usando as coordenadas X e Y. 
A área de desenho encontra-se entre 230 e -230 no eixo x e 170 e -120 no eixo y. 
Podemos usar esses valores em um bloco __se__, garantido que o mouse esteja dentro desta área antes de mover o lápis para o mouse.

Para isso, ponha um bloco __se__ ao redor de seu bloco existente __vá para.. se__ e dentro deste novo __se__ teste o seguinte:

mouse y é maior do que -120 e mouse y é inferior a 170
mouse x é superior a -230 e mouse x é inferior a 230

__Informação__ Para isso você vai precisar usar vários blocos do operador __e__, 
um para testar a posição x, outro para testar a posição y e outro para juntar os dois testes:


		limpe
		sempre 
		se < < <(mouse y) > (-120) > e <(mouse y) < (170)> >  e <  <(mouse  x) >  (-230)> e < (mouse x) < (230) > > >
		vá para [ponteiro do mouse v]


Como não é possível desenhar fora da área de desenho, podemos esconder o lápis sempre que ela estiver fora da área de trabalho. 
Para fazer isso, substitua o bloco __se__ por um bloco __ se .. senão__. 
Mantenha a mesma condição para o __se__ e faça com que o lápis __apareça__ se o teste for verdadeiro, e __desapareça__, caso contrário.


			quando BANDEIRA clicado
			levante a caneta
			limpe
			sempre
			se < < <(mouse y) > (-120) > e <(mouse y) < (170)> >  e <  <(mouse  x) >  (-230)> e < (mouse x) < (230) > > >
				vá para [ponteiro do mouse v]
				apareça
				se <mouse pressionado?>
					abaixe a caneta
				senão
					levante a caneta
				fim
			senão
				desapareça
			fim
		fim


### Teste o projeto
__Clique na bandeira verde.__

Você ainda pode desenhar dentro da área de desenho? 
Você pode desenhar fora da área de desenho? O que acontece com o lápis quando você sai da área de desenho e volta?

Salve o projeto

## Passo 5: Borracha

__Desenhar linhas é legal, mas às vezes também é preciso apagar linhas para corrigir erros.__ 
Nós podemos fazer isso com uma nova ferramenta do lápis que desenha na cor cinza (a mesma cor que o fundo).

Adicione um novo objeto para selecionar a borracha. Use __recurso/borracha__, 
diminua a borracha de tamanho para caber na parte de baixo do Palco. 
Ele deve funcionar da mesma maneira que os outros botões de seleção de cor, anunciando uma mensagem de borracha.

O lápis deve ouvir a mensagem __borracha_ e mudar a cor da caneta para cinza 
(lembre-se que você pode usar o __conta-gotas__ para selecionar a cor do plano de fundo). 
Você também precisa de um novo traje para representar a ferramenta borracha: use a mesma imagem __recursos/borracha__. 
__Lembre-se de redefinir o centro do traje.__

### Teste o projeto
__Clique na bandeira verde.__

A borracha apaga as linhas? Funciona até as bordas? Você pode alternar entre borracha e as outras cores de caneta?

Salve o projeto

##Passo 6: Carimbando

A próxima coisa a acrescentar é uma ferramenta de carimbo, para carimbar imagens no desenho.


1. Adicione um novo objeto, usando qualquer imagem ou traje que você quiser. 
Encolha o objeto e coloque-o na parte de baixo da tela, ao lado das outras ferramentas. 
Quando esse objeto for clicado, ele deve anunciar __carimbo__.
2. Adicione um novo traje para o lápis, o mesmo que você escolheu para o botão __carimbo__.
3. Selecione o objeto caneta e crie uma nova variável chamada __usando caneta__ __para este objeto apenas__. 
Usaremos esta variável para controlar se estamos desenhando ou carimbando.
4. Adicione um novo objeto para ouvir à mensagem __carimbo__. 
É preciso definir o traje para a carimbo e definir a variável __usando caneta__ para __falso__.
5. Altere os outros comandos que respondem às mensagens da ferramenta de seleção (vermelho, verde, azul e borracha), 
de modo que cada um defina o __usando caneta__ como __verdadeiro__.
6. Finalmente, vamos verificar essa variável __quando o botão do mouse é pressionado__ para ver se devemos desenhar ou carimbar.
Se o "usando caneta" = verdadeiro devemos usar o __abaixe a caneta__ já existente, senão devemos carimbar.

##Teste o projeto
__Clique na bandeira verde.__

A ferramenta carimbo funciona corretamente?

O que acontece quando você usa as cores do lápis?

Salve o projeto

__Parabéns, você completou os passos básicos deste projeto.
Experimente estes desafios!__

## Desafio 1: Caneta Arco-Íris

Vamos adicionar umo lápis especial que pinta nas cores do arco-íris. 
É algo que você não pode fazer com canetas e lápis comuns, por isso é bom para mostrar como desenhar em um computador permite 
fazer coisas diferentes. O segredo é usar o bloco __mude a cor da caneta por__.

Primeiro, adicione um objeto para o botão  arco-íris e o traje arco-íris para o lápis:

1. Crie um novo objeto ao lado de todos os outros objetos de seleção de cor do lápis. 
Use o traje recursos/botão-arco-íris e faça ele anunciar arco-íris quando clicado.
2. Adicione recursos/lápis-arco-lápis para o objeto lápis.

Você pode adicionar os blocos para mudar a cor da caneta muitas vezes por segundo para dar o efeito arco-íris 
(Mudar por 5 a cada 0,05 segundo funciona bem, mas você pode experimentar valores diferentes). 
O cartão de cronômetro do Scratch mostra como você pode fazer algo mudar de tempos em tempos. 
Use um bloco __mude a cor da caneta por (5)__, em vez do __mude [temporizador] por (-1)__ como é o caso do cartão.

Você também precisa controlar esta repetição para que ele só mude a cor da caneta quando o lápis arco-íris estiver selecionado, 
se você não fizer isso todas as cores terão um efeito arco-íris! 
Você pode fazer isso de uma forma semelhante à forma como mudamos entre os modos __carimbo__ e __caneta normal__. 
Você precisa criar uma variável chamada __mudar-arco-iris__ que tem o valor verdadeiro quando você quiser um efeito arco-íris e falso
 caso contrário. Cada vez que o lápis ouve a mensagem relacionada a uma ferramenta de desenho, 
 ela deve mudar a variável __mudar-arco-iris__ de acordo com cada caso.

Use o que você aprendeu com o carimbo no passo acima para controlar o efeito arco-íris.
 O bloco de comandos que ouve às mensagens ferramenta de seleção irá mudar duas variáveis: __usando caneta__ e __mudar-arco-iris__.

### Teste o projeto
__Clique na bandeira verde.__

A ferramenta do arco-íris funciona corretamente?

O que acontece quando você voltar a usar uma das ferramentas normais do lápis?

Salve o projeto

## Desafio 2: Atalhos de teclado

Ao invés de usar os objetos de seleção de ferramenta na parte de baixo do palco, 
você pode usar o teclado para selecionar as diferentes ferramentas.
Você pode usar o bloco __quando tecla [] pressionada__ ​​para reagir ao teclado. 
Para cada tecla que você quiser usar, você vai precisar de outro bloco __quando tecla [] pressionada__, 
que anuncia a mesma mensagem que o respectivo objeto de seleção de ferramenta faz quando clicado. Adicione esses comandos para o palco.

Nós usamos esses atalhos:

* Limpar - a
* Apagar - e
* Caneta Vermelha - r
* Caneta azul - b
* Caneta Amarela - y
* Caneta Verde - g
* Caneta arco-íris - w
* Carimbo - s

### Teste o projeto
__Clique na bandeira verde.__

Todos os atalhos de teclado estão corretos? Cada uma das ferramentas funciona corretamente quando você seleciona com o teclado?
 As ferramentas ainda são selecionadas corretamente usando os botões no palco?

Salve o projeto

## Desafio 3: Pequeno e Grande
Outra característica que a maioria dos pacotes de desenho tem é a capacidade de alterar o
tamanho do lápis. Vamos adicionar isso.
Há uma complicação: às vezes o redimensionamento precisa mudar o tamanho da caneta e às vezes ela precisa mudar o 
tamanho do traje do objeto lápis. Depende se você estiver usando a caneta ou o carimbo.

Crie dois objetos de seleção de ferramenta, chamados de maior e menor. 
Eles devem usar recursos/botão-maior e recursos/botão-menor e devem anunciar as mensagens maior e menor.

O objeto lápis pode ouvir às mensagens mudando o tamanho da caneta por 1 ou o tamanho do traje por 10, 
dependendo do valor do modo de lápis (use um bloco __se..senão__, parecido com o usado para abaixar a caneta ou carimbar)
Não esqueça os atalhos de teclado para as ferramentas  maior e menor. Nós usamos as setas para cima e para baixo.

Salve o projeto

O que você deve ter notado é que a mudança de tamanho do carimbo também altera o tamanho da caneta na tela quando você muda para a ferramenta.
Para impedir isso, você precisa definir o tamanho de 100% cada vez que você mudar para uma ferramenta de caneta. 
Desse modo as ferramentas vão aparecer com o tamanho certo.

Para torná-lo ainda melhor, você pode fazer com que o carimbo lembre o tamanho que tinha antes de você ter selecionado a caneta. 
Assim ele poderá voltar ao tamanho anterior quando você selecionar o carimbo novamente. 
A maneira mais fácil de fazer isso é criar uma nova variável chamada __tamanho do carimbo__, 
que é atualizada com o tamanho atual cada vez que o carimbo é redimensionada. 
Quando a ferramenta carimbo é selecionada, ela pode mudar o seu tamanho usando o valor desta variável.


##Teste o projeto
__Clique na bandeira verde.__

O controle de tamanho funciona para a caneta?

O que acontece se você mudar para o carimbo, alterar o tamanho e, em seguida, voltar para a caneta?

Salve o projeto


__Parabéns você terminou, agora você pode desfrutar do jogo!__


Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ na barra de menu!
