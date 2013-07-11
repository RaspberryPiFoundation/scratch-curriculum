Nível 2

#Peixe faminto

__Introdução:__
Vamos fazer o jogo do peixe faminto! Guia o grande peixe faminto tentando comer todas as presas que nadam à sua volta.

##PASSO 1: Criar o peixe grande e fazê-lo seguir o ponteiro do rato

__Vamos fazer o peixe faminto nadar pelo mar fora!__

1. Cria um novo projeto Scratch.

2. Clica em «o palco» e selecciona o separador «Cenários». Importa o cenário
«Natureza/underwater3» e remove o cenário «backdrop1». Muda o nome do cenário
para «debaixo de água».

3. Altera o nome do actor gato para «o peixe faminto».

4. Clica sobre o actor «o peixe grande» e depois sobre o separador «Trajes». Importa um novo traje a partir do ficheiro «Recursos/de boca aberta.png». Remove os dois primeiros trajes, ainda com o gato.

5. Altera o estilo de rotação do peixe grande para que olhe apenas para a esquerda ou para a direita.

6. Cria um guião como o que se segue para que o peixe faminto siga o ponteiro do rato pelo mar fora:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		aponta em direcção a [o ponteiro do rato ▼]
		anda (3) passos
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ Move o ponteiro do rato pelo mar. O peixe segue o ponteiro do rato? O que acontece quando deixas de mover o ponteiro do rato e o peixe o alcança? O que parece estar a acontecer? Por que é que isto acontece?

7. Podes fazer com que o peixe faminto pare de se virar de um lado para o outro como um louco se fizeres com que ele 
só se mova quando não estiver demasiado próximo do ponteiro do rato
(o bloco (a distância até [... ▼]) está na paleta «Sensores»).

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		se &lt;(a distância até [o ponteiro do rato  ▼]) > (10)>, então
			aponta em direcção a [o ponteiro do rato ▼]
			anda (3) passos
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ Move o ponteiro do rato pelo mar. O peixe segue o ponteiro do rato? O que acontece quando deixas de mover o ponteiro do rato e o peixe o alcança?

__Para parar, carrega no sinal de _stop_.__

###Coisas a experimentar

Se quiseres, podes tentar colocar diferentes valores no guião. De que forma
isso afecta o movimento do peixe faminto? Altera o limiar de distância para um
valor grande (por exemplo, 100) ou para um valor pequeno (por exemplo, 1).
Altere o número de passos que o peixe anda para um valor grande (por exemplo,
20) ou para um valor pequeno (por exemplo, 1 ou mesmo 0).

##PASSO 2: Adicionar uma presa

1. Cria um novo actor a partir da biblioteca: «Animais/Fish2». Altera o seu
nome para «a presa 1» e altera o nome do seu único traje para «normal».

2. Usa a ferramenta «Reduzir» (acima do palco) para reduzir o novo actor.

3. Cria um guião para fazer a presa nadar.  Queremos que a presa se mova
aleatoriamente, por isso vamos fazê-la girar um ângulo aleatório em qualquer
dos sentidos, avançar um pouco e ressaltar quando bater na borda do palco,
repetindo estes passos indefinidamente:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	mostra-te
	repete para sempre,
		gira ⟳ (um valor ao acaso entre (-10) e (10)) °
		anda (2) passos
		se estiveres a bater na borda, ressalta
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde e observa a presa a nadar.__ Nada como esperavas? Nada de forma realista?

__Neste momento, o peixe faminto e a presa não interagem um com o outro. Resolveremos o problema no próximo passo.__

__Para parar, carrega no sinal de _stop_.__

###Coisas a experimentar

* Tenta alterar os valores nos blocos (um valor ao acaso entre () e ()) e
[anda () passos]. De que forma essas alterações afectam o movimento da
presa?

* O que faz o comando [se estiveres a bater na borda, ressalta]?  Retira-o e
vê o que acontece.

##PASSO 3: O peixe faminto come a presa

__Agora queremos que o peixe faminto coma a presa!__ Assim que o peixe faminto
abocanhar a presa, duas coisas têm de acontecer:

- O peixe faminto precisa de fechar a boca e de fazer um som como se estivesse a engolir.

* A presa tem que desaparecer e, algum tempo depois, tem de reaparecer, como se fosse um novo peixe.

1. Vamos começar por fazer a presa desaparecer se estiver a tocar no peixe faminto, fazendo-a reaparecer três segundos depois. 
Usa o bloco &lt;estás a tocar em [o peixe faminto ▼]> para verificar se a presa está a tocar no peixe faminto:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	mostra-te
	repete para sempre,
		gira ⟳ (um valor ao acaso entre (-10) e (10)) °
		anda (2) passos
		se estiveres a bater na borda, ressalta
		se &lt;estás a tocar em [o peixe faminto ▼]>, então
			esconde-te
			espera (3) s
			mostra-te
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

### Testa o teu projecto

__Testa de novo o teu jogo.__ Detectas algum problema? Nota que a presa
desaparece assim que toca em qualquer ponto do peixe faminto. Além disso, o
peixe faminto pode limitar-se a esperar três segundos no mesmo local que
abocanhará imediatamente a (nova) presa logo que ela aparecer – não é assim
muito justo!

2. Como poderemos garantir que a presa só desaparece se estiver a tocar na
boca do peixe?  Podemos usar o bloco &lt;estás a tocar na cor []> para, verificar
se a presa, para além de estar a tocar no peixe faminto, está também a tocar
nos seus dentes azuis. Para fazer isto, transfere o bloco &lt;estás a tocar em [o
peixe faminto ▼]> para a primeira entrada de um novo bloco &lt;&lt;> e &lt;>> e coloca esse novo
bloco no comando [se &lt;>, então]. Na segunda entrada do bloco &lt;&lt;> e &lt;>> coloca
o bloco &lt;estás a tocar na cor []>. Clica no quadrado colorido dentro desse
bloco e, em seguida, clica nos dentes do peixe. A cor dos dentes preencherá o
quadrado colorido.

3. Agora podemos fazer a nova presa ir para um ponto aleatório do palco, antes de reaparecer, usando um comando [vai para as coordenadas (x: (), y: ())] e 
dando valores aleatórios às coordenadas x e y.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	mostra-te
	repete para sempre,
		gira ⟳ (um valor ao acaso entre (-10) e (10)) °
		anda (2) passos
		se estiveres a bater na borda, ressalta
		se &lt;&lt;estás a tocar em [o peixe faminto ▼]> e &lt;estás a tocar na cor [#003]>>, então
			esconde-te
			espera (3) s
			vai para as coordenadas (x: (um valor ao acaso entre (-220) e (220)), y: (um valor ao acaso entre (-170) e (170)))
			mostra-te
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

###Testa o teu projecto

__Experimenta o jogo mais uma vez.__ A presa só desaparece quando toca na boca
do peixe? A presa volta a aparecer num ponto aleatório do palco, e não no
mesmo local em que foi comido?

4. O peixe faminto precisa de saber quando comeu alguma coisa para que possa tocar um som apropriado e mudar de traje. 
Para isso, podemos fazer a presa, antes de desaparecer, difundir uma mensagem anunciando o facto de que foi comida.

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	mostra-te
	repete para sempre,
		gira ⟳ (um valor ao acaso entre (-10) e (10)) °
		anda (2) passos
		se estiveres a bater na borda, ressalta
		se &lt;&lt;estás a tocar em [o peixe faminto ▼]> e &lt;estás a tocar na cor [#003]>>, então
			difunde a mensagem [Eu, presa, fui comida! ▼]
			esconde-te
			espera (3) s
			vai para as coordenadas (x: (um valor ao acaso entre (-220) e (220)), y: (um valor ao acaso entre (-170) e (170)))
			mostra-te
		[fim do comando «se, então»]
	[fim do comando «repete para sempre»]
	[fim do guião]
```

__Agora queremos que o peixe faminto esteja atento a esta mensagem e, quando a
receber, faça o som de engolir e feche a sua boca.__

5. Adiciona o traje «Recursos/de boca fechada.png» e o som
«Recursos/engolindo.wav» ao actor «o peixe faminto». Aproveita para remover o
som «pop».

6. Agora, adiciona um novo guião ao peixe faminto para ouvir a mensagem
difundida pela presa e fazer o que é suposto quando a receber. Este guião deve
fazer o peixe faminto tocar o som «engolindo» e, por duas vezes, mudar
brevemente para o traje «de boca fechada»:

```scratch
	Quando receberes a mensagem [Eu, presa, fui comida! ▼]
	toca o som [engolindo ▼]
	repete (2) vezes
		muda o traje para [de boca fechada ▼]
		espera (0.2) s
		muda o traje para [de boca aberta ▼]
		espera (0.2) s
	[fim do comando «repete vezes»]
	[fim do guião]
```

__Agora que o nosso peixe faminto está preparado para comer, vamos encher o
oceano de presas.  Clica com o botão direito do rato sobre o actor «a presa 1»
e escolhe «duplicar». Faz isto várias vezes.__

###Testa o teu projecto

__Clica na bandeira verde.__ O peixe faminto come as presas? Consegue comer cada uma delas?

###Coisas a ponderar

Precisámos de colocar o comando [mostra-te] no início do guião da presa.
Porquê? Pensa no que aconteceria se a presa fosse comida e o jogo fosse
interrompido antes de a presa reaparecer. O que aconteceria se o jogo fosse
reiniciado?

__Parabéns! Terminaste o jogo básico. Mas há mais coisas a fazer. Estás pronto para o desafio?__

##DESAFIO 1: Dar um movimento diferente às presas

Neste momento, todas as presas se movem da mesma maneira. __És capaz de fazê-las moverem-se de forma diferente umas das outras?__

__Dica:__ Não passes muito tempo nesta parte sem antes olhares para as outras actividades deste projeto.

__Escolhe uma das presas para fazeres as tuas experiências.__ Como todas as presas são iguais, muda a cor desta presa usando o comando [altera o teu efeito de cor para (50)]. Coloca esse comando no início do guião dessa presa, para que o efeito seja aplicado sempre que o jogo é iniciado.
Dessa forma distinguirás a presa das experiências das outras presas.

Faz esta presa mover-se mais devagar que as outras. 

__Dica:__ Dá uma olhadela ao comando [anda (2) passos].

###Testa o teu projecto

A presa das experiências move-se mais devagar? O jogo melhorou com isso? Se
conseguiste reduzir a velocidade desta presa, __experimenta fazer uma das
outras presas mover-se mais depressa que todas as outras__. Dá-lhe também um
efeito de cor que a distinga das demais presas. Coloca esse comando no início
do guião dessa presa, para que o efeito seja aplicado sempre que o jogo é
iniciado.

As presas ainda se movem de forma correcta? O jogo melhorou?

__Dica:__ Se a presa nadar aos círculos, verifica os valores do bloco (um valor ao acaso entre () e ()) que está dentro do comando [gira ⟳ () °].

Que tal fazeres cada um das presas comportar-se de forma diferente das outras
usando diferentes combinações das mudanças que propusemos?

Alguma dessas alterações melhorou o jogo? As alterações fizeram o jogo mais
interessante, mais divertido, mais difícil ou mais fácil?

##DESAFIO 2: Fazer as presas fugir do peixe faminto

As presas neste jogo são realmente estúpidas! Limitam-se a nadar ao acaso até
serem comidas. Peixes reais fogem dos seus predadores. __Faz uma das presas
fugir do peixe faminto.__

Não há nenhum bloco no Scratch que reporte em que direcção se encontra um
outro actor. Mas podemos fazer um actor apontar para outro e, de seguida,
fazê-lo dar meia volta, ficando a apontar para o sentido oposto.  Os blocos de
que precisas estão na paleta «Movimento». Usando esta ideia, __faz uma das
presas apontar sempre para a direcção oposta à do peixe faminto__. Talvez
queiras fazer a presa serpentear um pouco enquanto foge, bem como fazê-la nadar mais depressa. Pode ser boa ideia
fazer a presa fugir apenas se estiver suficientemente perto do peixe faminto. Altera o efeito de cor da presa que foge para que a possas melhor identificar.

###Testa o teu projecto

Tornou-se mais difícil apanhar a presa que foge? O jogo melhorou?

##DESAFIO 3: Adicionar um painel de pontuação

Não é suficiente ter o peixe faminto a comer presas. Como podes saber se és
melhor jogador que os teus amigos? __Precisas de uma forma de manter uma
pontuação, por isso vamos adicionar um painel de pontuação.__ Dá uma olhada à
carta do Scratch __Manter Pontuação__ para ficares com uma ideia de como isso
se consegue. Onde deves colocar o comando que muda a pontuação?

__Dica:__ É usualmente boa ideia que seja o palco a preocupar-se com a
pontuação.

Assegura-te de que a pontuação é colocada a zero no início do jogo. Onde deves
colocar o comando de inicialização da pontuação?

###Testa o teu projecto

A pontuação inicia a zero quando o jogo começa? Aumenta de cada vez que o
peixe faminto come uma presa?

##DESAFIO 4: Adicionar uma contagem decrescente

__Estabelece um tempo limite para o jogo.__ Quantos peixes consegues comer em
trinta segundos?

Dá uma olhadela na carta Scratch __Cronómetro__ para veres como adicionar um
cronómetro ao jogo. Começa o jogo com uma duração de trinta segundos. Quando a
contagem decrescente terminar, pára o jogo.

### Testa o teu projecto

A contagem decrescente começa em 30 segundos? A contagem decrescente diminui à
velocidade certa? Consegues comer presas enquanto a contagem decrescente
diminui? O jogo termina quando a contagem descrescente atinge zero?

##DESAFIO 5: Adicionar um bónus

Atribui um bónus de tempo ao jogador se ele conseguir em algum momento comer
todos os peixes. Como é possível saber quantos peixes estão comidos em cada
instante?

__Dica:__ Uma solução é __usar uma variável para contar o número de presas vivas em cada momento__. Atenção! O bónus deve ser atribuído apenas uma vez de cada vez que as presas são todas comidas!

##DESAFIO 6: Inverte o jogo: mantém a presa viva!

Por vezes podes ter ideias excelentes invertendo uma ideia existente.

__Modifica o jogo para que, em vez de controlares um peixe faminto que tenta
comer as várias presas, passes a controlar uma presa isolada num mar com
vários peixes famintos.__ Quanto tempo aguentas sem seres comido?

__Parabéns! Terminaste! Agora pode desfrutar do jogo!__ Não te esqueças de que
podes partilhar o teu jogo com todos os Scratchadores, incluindo os teus
amigos e os teus familiares, clicando em «Partilhar»!
