Nível 3

# Ferramenta de desenho

__Introdução:__
Neste projeto nós vamos criar um a ferramenta de pintura para que você possa desenhar. Será possível escolher a cor do lápis, limpar a tela, usar carimbos e muito mais!

## PASSO 1: Arrastando e desenhando

Vamos começar com um lápis que risca quando arrastado sobre a tela.

1. Crie um novo projeto Scratch. Exclua o gato clicando com o botão direito e em apagar
2. Clique __Palco__ e, em seguida, na aba __Fundos de tela__ importe o fundo __indoors/chalkboard__.
3. Criar um novo objeto chamado __lápis__, utilizando __recursos/lápis-verde.__
4. Vá para a aba __trajes__, clique em Editar e faça com que o centro da imagem fique na ponta da caneta. Para fazer isso, clique em __selecionar centro do traje__, (no canto embaixo à esquerda) e arraste as linhas até que elas estejam na ponta do lápis.
5. Faça a caneta seguir
o mouse usando um bloco __sempre__
e um bloco __vá para [ponteiro do mouse]__


		quando BANDEIRA clicado
		sempre
			vá para [ponteiro do mouse v]
		fim


__Vamos fazer com que o objeto lápis se comporte como um lápis de verdade.__ Dê uma olhada na aba caneta e você verá vários blocos relacionados à pintura. Os blocos que nos interessam agora são  __abaixe a caneta__ e __levante a caneta__

6. Vamos usar o botão do mouse para controlar a caneta - sempre que o mouse estiver pressionado a caneta será abaixada, e quando não estiver clicado a caneta deve estar levantada. Podemos fazer isso usando o bloco __se ... senão__ e o bloco __mouse pressionado?__ .


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
A caneta segue o mouse? O que acontece se você segurar o botão do mouse pressionado e mover? Não se preocupe com a cor da caneta para enquanto.


7. Uma hora a tela vai ficar cheia de rabiscos. O bloco __limpe__ pode ser usada para limpar a tela.


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

Ao invés de ter que reiniciar o projeto para apagar os desenhos, vamos adicionar um botão para cancelar o desenho. Para fazer isso use o bloco __limpe__.

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

Até agora, só desenhamos linhas azuis. Que tal usarmos cores diferentes! 
Vamos adicionar alguns objetos na parte de baixo do quadro. Os objetos serão parecidos com botões coloridos. Quando você clicar em um dos botões, ele vai mudar a cor do lápis. O objeto lápis também mudará de cor para sabermos qual cor estamos usando.

1. Adicione um novo objeto, chamado __vermelho__, utilizando __recursos/botão-vermelho__.
2. Ele deve ser posto em algum lugar ao longo da parte de baixo do quadro, perto do botão __limpar__.
3. Quando o botão vermelho é clicado, ele deve anunciar a mensagem __vermelho__.


Quando vermelho clicado
anuncie [vermelho v] para todos

__Isso mesmo, são somente dois blocos. A parte complicada fica por conta da lápis.__

No lápis, importe um novo traje, __recursos/lápis-vermelho__. Selecione o centro do traje para que ele fique na ponta da caneta, da mesma maneira que você acabou de fazer parao traje original.

4. Adicionar novos comandos para a caneta. Quando a caneta receber a mensagem __vermelho__, deve mudar para o traje caneta-vermelha e mudar a cor da caneta para vermelho (usando o bloco __mude a cor da caneta para__).

__Dica:__ Se você clicar no quadrado colorido
no bloco __mude a cor da caneta para__, você pode
usar o conta-gotas e clicar sobre o botão vermelho para garantir que a caneta e o botão tenham a mesma cor.


quando eu ouvir [vermelho v]
mude para o traje

mude a cor da caneta para [#f00]


### Teste o projeto
__Clique na bandeira verde.__

Desenhe uma linha. Em seguida, clique sobre o botão para selecionar a cor vermelha e desenhar laus pouco mais. A caneta muda de traje? Ela desnha em vermelho agora? O risco sai da ponta da caneta?

Salve o projeto

5. Repita o que você acabou de fazer mas agora usando os botões azul, amarelo e verde.

##Testar o projeto
__Clique na bandeira verde.__

Todos os botões de cor funcionam? Todos eles mudam o traje da caneta para a cor certa? Eles fazem a caneta escrever na cor certa? O desenho sempre sai da ponta do lápis?

Salve o projeto

## Passo 4: Desenhando dentro da margem

Você já deve ter notado que você pode desenhar em todo o palco, mesmo na margem. Nós não queremos que isso aconteça. Queremos manter o desenho no meio do palco. Devemos então restringir a posição da caneta para a área de desenho - a parte cinza claro no Palco.


Lembre-se que o Scratch define pontos usando os eixos X e Y. A área de desenho encontra-se entre 230 e -230 no eixo x e 170 e -120 no eixo y. Podemos usar esses valores em um bloco __se__, garantido que o mouse esteja dentro desta área antes de mover a caneta para o mouse.

Para fazer isso, englobe um novo bloco __se__ em torno de seu bloco existente __va para.. se__ e dentro deste novo __se__ teste o seguinte:

mouse y é maior do que -120 e mouse y é inferior a 170
mouse x é superior a -230 e mouse x é inferior a 230

__Informação__ Para isso você vai precisar usar vários blocos do operador __e__, um para testar a posição x, outro para testar a posição y e outro para juntar os dois testes:


		limpe
		sempre 
		se < < <(mouse y) > (-120) > e <(mouse y) < (170)> >  e <  <(mouse  x) >  (-230)> e < (mouse x) < (230) > > >
		vá para [ponteiro do mouse v]


Como não podemos desenhar fora da área de desenho, podemos esconder a caneta sempre que ela estiver fora da área de trabalho. Para fazer isso, substitua o bloco __se__ por um bloco __ se .. senão__. Mantenha a mesma condição para o __se__ e faça com que a caneta__apareça__ se o teste for verdadeiro, e __desapareça__, caso contrário.


quando BANDEIRA clicado
levante a caneta
limpe
sempre
rato se y é maior do que -120 e rato y é inferior a 170 e um rato x é superior a -230 e rato x é inferior a 230
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

Você ainda pode desenhar dentro da área de desenho? Você pode desenhar fora da área de desenho? O que acontece com a caneta quando você deixar a área de desenho e volta?

Salve o projeto

## Passo 5: Borracha

__Desenhando linhas é legal, mas há momentos em que acontecem erros e você quer apagá-lo.__ Nós podemos fazer isso com uma nova ferramenta de caneta que desenha na cor cinza (a mesma cor que o fundo).

Adicione um novo objeto para selecionar a borracha. Use __recurso/borracha__, tornando-o menor para caber na parte inferior do Palco. Ele deve funcionar da mesma maneira que os outros botões de seleção de cor, anunciando uma mensagem de borracha.

A caneta deve ouvir a mensagem borracha mudando a cor da caneta para cinza (lembre-se que você pode usar o __conta-gotas__ para selecionar a cor do plano de fundo). Ele também vai precisar de um novo traje para representar a ferramenta da borracha: use o mesmos __recursos/borracha__. __Lembre-se de redefinir o centro do traje.__

### Teste o projeto
__Clique na bandeira verde.__

A borracha apagar linhas? Funciona até as bordas? Você pode alternar entre borracha e as outras cores de caneta?

Salve o projeto

##Passo 6: Carimbando

A próxima coisa a acrescentar é uma ferramenta de carimbo, para carimbar imagens pequenas no desenho.


1. Adicione um novo objeto, usando qualquer imagem ou traje que você quiser. Encolha o objeto e coloque-o na parte inferior da tela, ao lado das outras ferramentas. Quando esse objeto for clicado, ele deve anunciar __carimbo__
2. Adicione um novo traje para a caneta, o mesmo que o que você escolheu para o botão __carimbo__.
3. Selecione o objeto caneta e criar uma nova variável __modo caneta__ __para este objeto apenas__. Usaremos esta variável para controlar se estamos desenhando ou carimbando.
4. Adicione um novo objeto para ouvir à mensagem __carimbo__. É preciso definir o traje para a carimbo e definir a variável __modo caneta__ para __falso__.
5. Altere os outros comandos que respondem às mensagens da ferramenta de seleção (vermelho, verde, azul e borracha), de modo que cada um defina o __modo caneta__ como __verdadeiro__.
6. Finalmente, vamos verificar issa variável __quando o botão do mouse é pressionado__ para ver se devemos desenhar ou carimbar. Se o modo de lápis = verdadeiro devemos usar o __abaixe a caneta__ já existente, senão devemos carimbar.

##Teste o projeto
__Clique na bandeira verde.__

A ferramenta carimbo funciona corretamente?

O que acontece quando você tenta usar as cores da caneta?

Salve o projeto

__Parabéns, você completou os passos básicos para este projeto.
Experimente estes desafios!__

## Desafio 1: Caneta Arco-Íris

Vamos adicionar uma caneta especial que pinta em cores do arco-íris. É algo que você não pode fazer com canetas e lápis comuns, por isso é bom para mostrar como desenhar em um computador permite fazer coisas diferentes. O segredo para fazê-lo funcionar é bloco __mude a cor da caneta por__.

Primeiro, adicione o objeto de seleção do arco-íris e o traje arco-íris para a caneta:

1. Crie um novo objeto e coloque-o no palco, ao lado de todos os outros objetos de seleção de cor da caneta. Usar traje a recursos/arco-iris e faça ele anunciar arco-iris quando clicado.
2. Adicione recursos/arco-lápis para o objeto caneta.

Você pode adicionar os blocos para mudar a cor da caneta muitas vezes por segundo para dar o efeito arco-íris (Mudar por 5 a cada 0,05 segundo funciona bem, mas você pode experimentar valores diferentes). O cartão de temporizador do Scratch mostra como você pode fazer algo mudar de tempos em tempos. Use um bloco __mude a cor da caneta por (5)__, em vez do __mude [temporizador] por (-1)__ como é o caso do cartão.

Você também precisa controlar esta repetição para que ele só muda a cor da caneta quando você selecionou a caneta arco-íris, se você não fizer isso todas as cores terão um efeito arco-íris! Você pode fazer isso de uma forma semelhante à forma como mudamos entre os modos __carimbo__ e __caneta normal__. Você precisa criar uma variável chamada __mudar-arco-iris__ que tem o valor verdadeiro quando você quiser um efeito arco-íris e falso caso contrário. Cada vez que a caneta ouve a mensagem relacionada a uma ferramenta de desenho, ela deve mudar a variável __mudar-arco-iris__ de acordo com cada caso.

Use o que você aprendeu com o carimbo no passo acima para controlar o efeito arco-íris. O bloco de comandos que vou às mensagens ferramenta de seleção irá mudar duas variáveis: __modo caneta__ e __mudar-arco-iris__.

### Teste o projeto
__Clique na bandeira verde.__

A ferramenta do arco-íris funciona corretamente?

O que acontece quando você voltar para uma das ferramentas normais da caneta?

Salve o projeto

## Desafio 2: Atalhos de teclado

Ao invés de usar os objetos de seleção de ferramenta na parte inferior do palco, você pode usar o teclado para selecionar as diferentes ferramentas.
Você pode usar o bloco quando tecla [] pressionada ​​para reagir ao teclado. Para cada tecla que você quer usar, você vai precisar de outro bloco quando tecla [] pressionada, que anuncia a mesma mensagem que o respectivo objeto de seleção de ferramenta faz quando clicado. Adicione esses comandos para o palco.

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

Todos os atalhos de teclado estão corretos? Cada uma das ferramentas funciona corretamente quando você seleciona usando o teclado? As ferramentas ainda são selecionadas corretamente usando os botões no palco?

Salve o projeto

## Desafio 3: Pequeno e Grande
Outra característica que a maioria dos pacotes de desenho tem é a capacidade de alterar o
tamanho da caneta. Vamos adicionar isso.
Há uma complicação, porém, porque às vezes o redimensionamento precisa mudar o tamanho da caneta e às vezes ela precisa mudar de tamanho traje do objeto caneta. Depende se você estiver usando a caneta ou o carimbo.

Crie dois objetos de seleção de ferramenta, chamados de maior e menor. Eles devem usar recursos/maior e rescursos/menor devem anunciar as mensagens maior e menor.

O objeto caneta pode ouvir às mensagens alterando o tamanho da caneta por 1 ou o tamanho do traje por 10, dependendo do valor do modo de lápis (use um bloco __se..senão__, parecido com o usado para abaixar a caneta ou carimbar)
Não esqueça os atalhos de teclado para as ferramentas de maiores e menores. Eu usei as setas para cima e para baixo.

Salve o projeto

O que você deve ter notado é que a mudança do tamanho do carimbo também altera o tamanho da caneta na tela quando você muda para a ferramenta.
Para impedir isso, você precisa definir o tamanho de 100% cada vez que você mudar para uma ferramenta de caneta. de modo que as ferramentas apareçam com o tamanho certo.

Para torná-lo ainda melhor, você pode fazer com que o carimbo lembre o o tamanho que tinha antes de você ter selecionad a caneta e voltar para o tamanho anterior quando você selecionar o carimbo novamente. A maneira mais fácil de fazer isso é criar uma nova variável chamada tamanhoCarimbo, que é atualizado com o tamanho atual cada vez que o carimbo é redimensionada. Quando a ferramenta carimbo é selecionada, ele pode mudar o seu tamanho usando o valor desta variável.


##teste o projeto
__Clique na bandeira verde.__

O controle de tamanho funciona para a caneta?

O que acontece se você mudar para o carimbo, alterar o tamanho e, em seguida, voltar para a caneta?

Salve o projeto


__Parabéns você terminou, agora você pode desfrutar do jogo!__


Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ na barra de menu!
