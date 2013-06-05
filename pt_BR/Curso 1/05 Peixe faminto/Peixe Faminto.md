Nível 2

#Peixe Faminto


__Introdução:__

Neste jogo voce deve orientar o grande peixe faminto e tentar comer todas as presas que estão nadando ao redor.

## PASSO 1: Crie um objeto que muda de traje
__Vamos fazer este peixe faminto nadar no mar!__

1. Crie um novo projecto Scratch.
2. Clique no Palco, selecione a aba fundos de tela. Importe o
Fundo nature/underwater e apague o fundo de tela1.
3. Apague o gato.
4. Importe o objeto a partir do arquivo Recursos/Peixe Faminto
5. Use o botão acima da aba Trajes para certificar-se o objeto só pode virar de esquerda-direita.
6. Agora crie os comandos para que o Peixe Faminto siga o mouse pelo mar:



		quando BANDEIRA clicado
		sempre	
			aponte para [ponteiro do mouse v]
			mova (3) passos
		fim


### Teste o projeto
__Clique na bandeira verde.__
Mova o ponteiro do mouse pelo mar. O peixe segue o ponteiro do mouse?
O que acontece se você não mover o ponteiro do mouse e o peixe o alcança? O que esta acontecendo? Por que isso acontece?


7. Você pode fazer o Peixe Faminto parar de virar feito louco como um louco se você fizer ele só se move quando não estiver muito próximo do ponteiro do mouse
(O bloco __distância até__ está na aba sensores
.




		quando BANDEIRA clicado
		sempre se < (distância até [ponteiro do mouse v])  > (10) >
			aponte para [ponteiro do mouse v]
			mova (3) passos
		fim



### Teste o projeto

Salve o projeto

### Sugestões

Se você quiser, você pode testar diferentes valores nos comandos. Como isso muda a maneira que o Peixe Faminto se move? Altere o limite de distância para um número grande (por exemplo 100), ou um número pequeno (por exemplo, 1). Altere a quantidade de passos que o peixe se move um grande número (por exemplo 20) ou um pequeno número (por exemplo, 1 ou mesmo 0).


## Passo 2: Adicione umas presas

1. Crie um novo objeto do arquivo animals/lobster1.
2. Use a ferramenta Encolher Objeto (acima do palco)
para fazer a camarão ficar menor.
3. Criar os comandos para fazer a presa nadar. Queremos que eles se mocam aleatoriamente, então vamos fazê-lo avançar um pouco, em seguida, vire uma quantidade aleatória para a esquerda ou para a direita, repetindo isso novamente



		quando BANDEIRA clicado
		sempre	
			mova (2) passos 
			vire cw (sorteie número entre (-20) e (20) ) graus
			se tocar na borda, volta
		fim


### Teste o projeto
__Clique na bandeira verde e observe as presas nadando.__ Elas nadam como você esperava? Elas nadam de uma forma realista?

__Até agora o Peixe Faminto e as presas não interagem uns com os outros__. Vamos resolver isso na próxima etapa.

Salve o projeto

### Sugestões

* Tente alterar os valores nos blocos __sorteie__ e __mova__. Como isso muda a forma que as presas se movimentam?
* O que o __se tocar na borda, volta__ faz? Retire-o e veja o que acontece.

##PASSO 3: Peixe come as presas

__Vamos fazer o Peixe Faminto comer as presas!__ Uma vez que o Peixe Faminto tem uma presa em sua boca, duas coisas precisam acontecer:
* O Peixe Faminto precisa fechar a boca e fazer um som "chomp".
* A presa tem de desaparecer, e reaparecer um pouco mais tarde.

1. Primeiro, vamos fazer a presa desaparecer se ele está tocando o peixe com fome, e reaparecer 3 segundos depois. Use o bloco __tocando__ para ver se ele está tocando o peixe.



		quando BANDEIRA clicado
		sempre	
			mova (2) passos 
			vire cw (sorteie número entre (-20) e (20) ) graus
			se tocar na borda, volta
			se <tocando em [Peixe Faminto v]
				desapareça
				espere (3) segundos
				apareça
			fim
		fim


### Teste o projeto
__Teste o jogo novamente - você pode detectar eventuais problemas?__ Observe que a presa desaparece, não importa onde ele toca o peixe. Além disso, o peixe poderia apenas aguarde 3 segundos e comer a presa no momento em que reaparece - isso não é muito justo!

2. Como podemos garantir que a presa só desaparece se ela está tocando a boca do peixe? Bem, nós poderíamos usar o bloco __tocando na cor__, e ver se ele está tocando os dentes azuis do peixe. Para fazer isso, substitua o bloco __tocando em__ por um
bloco __tocando na cor__, clique na cor dentro do bloco e, em seguida, clique novamente nos dentes do peixe.
3. Em seguida, podemos fazer a presa ir a um ponto aleatório na tela antes de reaparecer novamente, usando um bloco __vá para__ e dando valores aleatórios
para x e y.



		quando BANDEIRA clicado
		sempre	
			mova (2)  passos
			vire cw (sorteie número entre (-20) e (20) ) graus
			se tocar na borda, volta
			se <tocando na cor [#003]?>
				desapareça
				espere (3) segundos
				vá para x: (sorteie número entre (-220) e (220)) y:(sorteie número entre (-170) e (170))
				apareça
			fim
		fim

### Teste o projeto

Experimente o jogo mais uma vez - as presas só desaparecem quando tocam a boca do peixe? E elas voltam a aparecer em um ponto aleatório da tela ao invés de onde foi comido?

4. O peixe precisa saber quando ele comeu alguma coisa para que ele toque um som e mude de traje. Para fazer isso, nós podemos fazer a presa anunciar o fato de que ela foi comida antes de desaparecer.



		quando BANDEIRA clicado
		sempre	
			mova (2) passos
			vire cw (sorteie número entre (-20) e (20) ) graus
			se tocar na borda, volta
			se <tocando na cor [#003]?>
				anuncie [me pegou] para todos
				desapareça
				espere (3) segundos
				vá para x: (sorteie número entre (-220) e (220)) y:(sorteie número entre (-170) e (170))
				apareça
			fim
		fim

__Agora vamos fazer o peixe ouvir esta mensagem
fazendo um som de "morder" e fechando suas mandíbulas.__

5. Adicione o traje __Recursos/boca fechada__ e o som recursos/chomp para o objeto Peixe Faminto.
6. Em seguida, adicione novos comandos para o Peixe Faminto para ouvir a mensagem transmitida pela presa. Este script deve fazer o peixe reproduzir o som 'chomp' e mudar para o traje boca fechada, esperar um pouco e depois voltar.



		quando eu ouvir [me pegou]
		toque o som [chomp v]
		repita (2)
			mude para o traje [boca fechada v]
			espere (0.5) segundos
			mude para o traje [boca aberta v]
		fim


__Agora nosso peixe faminto está pronto para comer, vamos encher o oceano de presas. Clique com o botão direito do mouse sobre o objeto presa e clique em "duplicar" várias vezes.__

### Teste o projeto
Clique na bandeira verde.
O Peixe Faminto come as presas? Ele consegue comer cada uma das presas?

Salve o projeto

### Sugestões
Por que precisamos adicionar o bloco apareça no o início dos comandos da presa? Pense no que aconteceria se a presa fosse comida, e então o jogo fosse interrompido antes dela reaparecer. O que aconteceria se o jogo fosse reiniciado?

__Parabéns você terminou o jogo básico. Há mais coisas que você pode fazer para o seu jogo. Você está pronto para o desafio?__


## Desafio 1: Faça as presas se moverem de maneira diferente

Neste momento, toda a presa se movem da mesma maneira. __Você é capaz de fazê-las mover
de forma diferente?__
__Dica:__ Não passe muito tempo nesta parte, sem olhar para os outros desafios deste projeto.


__Escolha uma das presas para experimentar.__Como todas as presas são iguais, mude a cor da presa que você vai modificar, e aplique um efeito de cor usando o __bloco mude o efeito [cor] para__. Dessa forma, você pode distingui-la das demais.

Faça esta presa se mover mais devagar que as outras. __Dica:__ De uma olhada no bloco __mova (2) passos__.


### Teste o projeto
A presa se move mais devagar? O jogo ficou melhor?
Se voce consegui fazer isso então, __tente fazer uma presa se mover mais rapido as outras.__


As presas ainda se movem de uma maneira correta? Estas mudanças amelhoram o jogo?
__Dica:__ Se a presa nada em círculos, verifique os valores do bloco __sorteie número__ dentro do bloco __vire__ .

Que tal você fazer cada um das presas se comportar de forma diferente, usando diferentes combinações dessas mudanças?

Fazer qualquer uma dessas alterações tornar o jogo melhor? Eles fazem o jogo mais interessante, mais divertido, mais difícil, ou mais fácil?

Salve o projeto

##Desafio 2: Faça a presa fugir do peixe

As presas neste jogo são realmente burras! Elas simplesmente nadam ao redor aleatoriamente até que sejam comidas. Peixes de verdade fogem dos predadores. __Faça uma das presas fugir do Peixe Faminto.__

Não há nenhum bloco no Scratch que indica em que direção está um outro objeto. Mas você pode fazer um objeto apontar para outro, em seguida, ele pode dar meia volta e fugir. Os blocos que você precisa estão na aba __Movimento__.

Usando essa idéia, __faça uma das presas sempre apontar para a oposição oposta do Peixe com fome.__ Você pode querer fazê-lo nadar para longe.

### Teste o projeto
Ficou mais difícil de pegar a presa? O jogo ficou melhor?

Salve o projeto

##Desafio 3: Adicionar um placar
Não é suficiente apenas comer peixes. Como é que você faz para saber se joga melhor que o seus
amigos? __Voce precisa encontrar uma maneira de manter a pontuação, então vamos adicionar um quadro de pontuação.__Dê uma olhada no cartão Scratch __Conta pontos__ para uma idéia de como fazê-lo.

Onde você deve colocar o bloco que muda a pontuação?

Certifique-se que a pontuação vai de volta para zero no início do jogo. Onde você deve colocar esse bloco?

### Teste o projeto
A pontuação volta para zero no início do jogo? Ela aumenta cada vez que você come presa?

Salve o projeto

##Desafio 4: Adicione uma contagem regressiva

__Estabeleça um tempo limite para o jogo.__ Quantos peixes você pode comer em trinta
segundos?

Olhe o Cartão __cronômetro__ para saber como adicionar um cronômetro no jogo. Comece o jogo com uma duração de trinta segundos.

### Teste o projeto
O cronômetro começa em 30?

Ele diminui na velocidade certa?

Você pode capturar presas enquanto o cronômetro diminui?

O jogo termina quando o cronômetro chega a zero?

Salve o projeto

## Desafio 5: Adicione um bônus
Atribua um grande bônus se você comer todos os peixes ao mesmo tempo. Como é possível
saber quantos peixes foram comidos?
__Dica:__ Uma maneira de fazer isso é __usar uma variável para contar quantas presas estão nadando vivas.__

Salve o projeto

##Desafio 6: Mude o jogo: mantenha a presa viva! Às vezes, você pode ter novas idéias partindo de uma idéia existente e fazendo o oposto.

__Modifique o jogo para que, ao invés de você controlar um peixe que tenta comer os outros, você controla uma presa em um mar com vários peixes famintos.__Quanto tempo você pode sobreviver antes de ser comido?

Salve o projeto

__Parabéns, você terminou, agora você pode desfrutar do jogo!__
Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ na barra de menu!
