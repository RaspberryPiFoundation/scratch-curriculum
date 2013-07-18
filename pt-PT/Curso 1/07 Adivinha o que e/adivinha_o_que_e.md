Nível 3

#Adivinha o que é!

__Introdução:__ Um objecto aleatório é mostrado, todo distorcido, sobre um
quadro preto. Tens de adivinhar que objecto é e clicar na imagem
correspondente. Quanto mais depressa adivinhares, maior será a tua pontuação!

##PASSO 1: Fazer objectos diferentes surgirem no quadro preto

Queremos que umas quantas imagens diferentes apareçam sobre o quadro preto.

1. Cria um novo projeto Scratch e remove o actor gato.

2. Clica sobre «o palco» e, em seguida, clica no separador «Cenários». Importa
o cenário «Interior/chalkboard». Altera o nome do novo cenário para «sala com
quadro preto».

3. Importa um novo actor a teu gosto, por exemplo da pasta «Coisas». Altera o
nome desse actor para «a imagem». Vai para o separador «Trajes». Se o actor
que importaste tiver mais do que um traje, remove todos os trajes com excepção
do que mais te agradar. Altera o nome desse traje para descrever bem a imagem.

4. Posiciona o novo actor no meio do quadro preto. Se necessária, ajusta o seu
tamanho.

5. Clique de novo no separador «Trajes». Cria quatro novos trajes, importando
imagens à tua escolha. Dá nomes apropriados aos trajes criados. Usa o editor
de pintura para alterar os tamanhos relativas das imagens para que fiquem
todas com um tamanho semelhante sobre o quadro preto.

6. Vamos agora fazer surgir uma imagem aleatória. Cria o seguinte guião para o
actor «a imagem»:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete (um valor ao acaso entre (1) e (5)) vezes
		passa para o próximo traje
	[fim do comando «repete vezes»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ A imagem mudou? Se não, porquê?

__Clia sobre a bandeira verde mais algumas vezes.__ Surgem imagens diferentes?
Por vezes aparece a mesma imagem várias vezes seguidas, mas isso não é um
problema. Também reparou que a imagem «treme» até chegar à imagem final.
Corrigiremos isso na próxima etapa.

##PASSO 2: Distorcer as imagens

__Vamos agora distorcer a imagem que aparece e ir reduzindo essa distorção
durante alguns segundos até surgir a imagem original, sem distorções.__ Vamos
usar uma variável para controlar o grau de distorção existente. Se o valor da
variável for alto, haverá muita distorção.  À medida que o valor da variável
diminui a distorção torna-se cada vez menor. O grau de distorção guardado na
variável funcionará também como um cronómetro e servirá para atribuir pontos
ao jogador.

1. No separador «Dados», cria uma variável chamada «a distorção» apenas para o
actor corrente.

2. Altera o guião de modo a ficar assim:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete (um valor ao acaso entre (1) e (5)) vezes
		passa para o próximo traje
	[fim do comando «repete vezes»]
	altera [a distorção ▼] para [101]
	até que <(a distorção) = [0]>, repete
		adiciona a [a distorção ▼] o valor (-1)
		altera o teu efeito [pixelização ▼] para (a distorção)
		altera o teu efeito [cor ▼] para (a distorção)
		mostra-te
		espera (0.1) s
	[fim do comando «até que, repete»]
	[fim do guião]
```

Os novos blocos a inserir são o [esconde-te], no topo, bem como todos os
blocos com início em [altera [a distorção ▼] para [101]].

###Testa o teu projecto

__Clica na bandeira verde.__ Aparece uma imagem aleatória e distorcida? A
distorção diminui aos poucos? O valor da variável «a distorção» diminui à
medida que a imagem fica menos distorcida? Quando esse valor atinge zero a
imagem fica sem distorções? Obténs uma imagem aleatória cada vez que clica na
bandeira verde?

###Coisas a experimentar

__Modifica a distorção inicial bem como a quantidade de distorção reduzida a
cada passo.__ De que modo isso afecta a forma como a imagem é mostrada? Essas
modificações tornam mais difícil ou mais fácil perceber de que imagem se
trata?

__Experimenta outros efeitos gráficos.__ Afectam a dificuldade do jogo?

##PASSO 3: Permitir ao jogador adivinhar a imagem

Neste momento temos uma imagem aleatória que vai sendo revelada lentamente, à
medida que diminui o valor numa variável que controla a distorção. Mas como é
que se joga? Adicionaremos alguns actores na parte de baixo do palco para que
o jogador possa clicar neles. Se clicar no correcto, ganha. Se carrega no
errado, esse actor desaparece e o jogo continua.

Primeiro, no entanto, precisamos de saber qual é a resposta certa.

1. Cria uma nova variável chamada «a resposta correcta». Certifica-te que a
opção «Para todos os actores» está seleccionada.

2. Altera o guião que criaste de modo a guardar a resposta correcta na variável.
Adiciona o comando [altera [a resposta correcta ▼] para (o número do traje)]
logo após o primeiro comando de repetição:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete (um valor ao acaso entre (1) e (5)) vezes
		passa para o próximo traje
	[fim do comando «repete vezes»]
	altera [a resposta correcta ▼] para (o número do traje)
	altera [a distorção ▼] para [101]
	até que <(a distorção) = [0]>, repete
		adiciona a [a distorção ▼] o valor (-1)
		altera o teu efeito [pixelização ▼] para (a distorção)
		altera o teu efeito [cor ▼] para (a distorção)
		mostra-te
		espera (0.1) s
	[fim do comando «até que, repete»]
	[fim do guião]
```

__Agora vamos criar os objetos nos quais o jogador poderá clicar.__

3. Duplica o actor «a imagem» e move-a para o canto inferior esquerdo do
palco.

4. Renomeia esse actor para «a resposta 1». Isto faz com que seja mais fácil
reconhecê-lo.

5. Remove todos todos os guiões de «a resposta 1» e todos os seus trajes, com
excepção do primeiro.

6. Repete estes três últimos itens colocando «a resposta 2» ao lado de «a
resposta 1» e removendo tudo, excepto o segundo traje.

7. Repete isto mais três vezes para obteres «a resposta 3», «a resposta 4» e
«a resposta 5».

Deves terminar com uma fila de cinco actores de resposta no palco, cada uma
mostrando uma imagem correspondente a uma resposta possível. __Nenhum dos
actores de resposta pode ter guiões dentro dele!__

Agora, vamos fazer cada um dos actores de resposta reagir ao clique de acordo
com a correcção da resposta.

8. Adiciona este guião ao actor «a resposta 1»:

```scratch
	Quando alguém clicar em ti
	se <(a resposta correcta) = [1]>, então
		difunde a mensagem [O jogador acertou! ▼]
	senão
		esconde-te
	[fim do comando «se então senão»]
	[fim do guião]
```

9. Arrasta este guião para cima de cada um dos outros actores de resposta na
área dos actores. __Em cada um desses actores, substitui o valor 1 no guião
que copiaste pelos valores 2, 3, e assim sucessivamente.__

10. Agora temos de acrescentar algo que ouça a mensagem «O jogador acertou!» e
lhe dê a resposta apropriada. Volte para o actor «a imagem», o actor que é
mostrado no quadro preto. Adiciona este outro guião:

```scratch
	Quando receberes a mensagem [O jogador acertou! ▼]
	diz (a junção de [Parabéns! Acertaste! A tua pontuação é: ] com [a distorção])
	[fim do guião]
```

###Testa o teu projeto

__Clica na bandeira verde.__ O que acontece quando clicas na __resposta certa__?
O que acontece quando clicas na resposta __errada__? O que acontece ao actor da
resposta errada quando __começas um novo jogo__?

O teste revela dois problemas. Primeiro, respostas erradas não reaparecem
quando recomeças o jogo.  Segundo, a distorção não pára de diminuir quando o
jogador clica na resposta certa.

11. Para resolver o primeiro problema, adiciona o seguinte guião a cada um dos
cinco actores de resposta:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	mostra-te
	[fim do guião]
```

Para resolver o segundo problema, temos de parar a repetição do actor «a
imagem» assim que o jogador clicar na resposta certa. Vamos usar uma nova
variável chamada «o jogador acertou» para o conseguir.  Vamos inicializar essa
variável com o valor «falso» quando o jogo começar e alterar o seu valor para
«verdadeiro» quando o jogador acertar.  Vamos também fazer com que o ciclo de
repetição [até que &lt;>, repete []] pare não apenas quando a distorção chega a
zero, mas também quando a variável «o jogador acertou» tiver o valor
«verdadeiro».

12. Cria uma nova variável chamada «o jogador acertou» _apenas para o actor «a
imagem»_.

13. Alterar os guiões desse mesmo actor para ficarem como se segue:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	esconde-te
	repete (um valor ao acaso entre (1) e (5)) vezes
		passa para o próximo traje
	[fim do comando «repete vezes»]
	altera [a resposta correcta ▼] para (o número do traje)
	altera [o jogador acertou ▼] para [falso]
	altera [a distorção ▼] para [101]
	até que <<(a distorção) = [0]> ou <(o jogador acertou) = [verdadeiro]>>, repete
		adiciona a [a distorção ▼] o valor (-1)
		altera o teu efeito [pixelização ▼] para (a distorção)
		altera o teu efeito [cor ▼] para (a distorção)
		mostra-te
		espera (0.1) s
	[fim do comando «até que, repete»]
	[fim do guião]

	Quando receberes a mensagem [O jogador acertou! ▼]
	altera [o jogador acertou ▼] para [verdadeiro]
	cancela os teus efeitos gráficos
	diz (a junção de [Parabéns! Acertaste! A tua pontuação é: ] com [a distorção])
	[fim do guião]
```

14. Aproveita para deixar de mostrar no palco os monitores das variáveis «a
resposta correcta» e «o jogador acertou». Para isso basta desmarcares as
caixas de selecção junto aos blocos dessas variáveis na paleta de dados.
Quanto ao monitor da variável «a distorção», clica sobre ele com o botão
direito do rato e escolhe «large readout». Verás que a distorção decrescente,
que é também a quantidade de pontos que o jogador pode obter, ficará com muito
melhor aspecto!

__Parabéns! Terminaste o jogo básico!__

No entanto, há mais coisas que podes fazer neste jogo. Dá uma olhada nos
desafios!

##DESAFIO 1: Faz o jogo mais difícil ou mais fácil

Altera a dificuldade do jogo:

- Tenta alterar a velocidade a que a imagem é revelada, ou seja, a velocidade
a que diminui a pontuação que o jogador pode ganhar.

- Altera o tipo de distorções da imagem. Por exemplo, podes também rodá-la.

- Substitui as imagens a adivinhar de modo a que sejam mais semelhantes ou
mais diferentes entre si. Se fizeres isto, não te esqueças de alterar o
traje nos actores de resposta afectados!

##DESAFIO 2: Distorce a imagem de forma diferente em cada jogada

Neste momento, cada jogada usa a mesma distorção.  No passo 2, podes ter
tentado alguns efeitos diferentes que funcionam tão bem quanto os efeitos de
cor e de pixelização.

Procura algumas distorções diferentes e que funcionem bem.

Altera o jogo para que, em cada jogada, use uma distorção diferente no ciclo de
distorções decrescentes.

__Dica:__ Cria uma nova variável chamada «o tipo de distorção». Faz com que ela
tenha um valor aleatório no início de cada jogada. Usa comandos [se &lt;>, então
[] senão, []] dentro do ciclo de distorção para aplicar o tipo de distorção que
foi escolhida aleatoriamente para a jogada em curso.

##DESAFIO 3: Faz um jogo com várias jogadas

Até aqui, cada jogada é independente. Modifica o jogo para que possamos ter
várias jogadas. Por exemplo, num jogo de três jogadas o jogador tem de
adivinhar três imagens e pode obter até 300 pontos.

__Dica:__ Precisas de uma variável extra para armazenar o total geral de todas
as jogadas.  Também precisas de um bloco de repetição para repetires as
diferentes jogadas.

__Dica:__ Também deverás fazer os actores de resposta correspondentes a
respostas erradas reaparecerem no início de cada jogada.  Talvez possas
difundir uma mensagem para isso.

##DESAFIO 4: Faz as jogadas cada vez mais difíceis

Torna o jogo cada vez mais difícil a cada jogada.

Cada jogada deve valer a mesma quantidade de pontos?  Deves ganhar mais pontos
se responderes rapidamente nas jogadas finais, se estas forem mais difíceis.

__Dica:__ Como podes saber qual é a jogada actual? Como podes usar essa
informação para alterar a dificuldade e a relação entre o grau de distorção e
a pontuação?

##DESAFIO 5: Faz o jogo continuar até o jogador errar

Em vez de usar um número fixo de jogadas, faz com que o jogo continue até que o
jogador erre uma imagem. Isto provavelmente só funciona bem se o jogo for
ficando cada vez mais difícil.

##DESAFIO 6: Aumenta ou diminui a dificuldade consoante os resultados

Em vez de ir tornando o jogo mais difícil, faz com que o jogo ajuste a sua
dificuldade de acordo com os resultados do jogador.  Se o jogador acertar
rapidamente na imagem, torna a próxima jogada um pouco mais difícil.  Se ele
errar a imagem ou se demorar muito tempo até acertar, faz a próxima jogada um
pouco mais fácil.

Esta ideia só funciona se não acumulares a pontuação ao longo de várias jogadas.

##DESAFIO 7: Guarda a maior pontuação

Guarda a maior pontuação obtida no jogo. Se o jogador acertar e conseguir
ultrapassar a pontuação máxima, pergunta o seu nome e actualiza a maior
pontuação. Encontra uma forma de mostrares a maior pontuação e o nome da pessoa
que a obteve.

##DESAFIO 8: Faz com que errar custe pontos

De momento não há qualquer penalidade quando o jogador erra. Altera o jogo de
modo a que a pontuação total diminua sempre que o jogador erre.

Esta alteração torna o jogo mais interessante?

__Parabéns! Terminou! Agora podes desfrutar do jogo!__

Não te esqueças que podes partilhar o teu jogo com outros Scratchadores,
incluindo os teus amigos e os teus familiares, clicando em «Partilhar»!
