Nível 2 

#Jogo das frutas (máquina caça-níquel)

__Introdução:__ Este jogo simula uma máquina caça-níquel (ou _slot machine_) com
três rodas de figuras. Essas rodas vão rodando, variando a figura de cada uma
dessas rodas que é visível no mostrador da máquina. Para ganhar o jogo, o
jogador tem de interromper a rotação das rodas quando as figuras visíveis forem
todas iguais.

Vamos usar três actores para representar as três rodas da máquina e diferentes
trajes dos actores para representar as figuras impressas em torno das rodas.

##PASSO 1: Criar um actor que muda de traje

__Vamos começar por importar as diferentes imagens do jogo.__

1. Cria um novo projecto Scratch. Remove o actor gato clicando nele com o botão direito do rato e escolhendo «remover».

2. Cria um novo actor importando-o da biblioteca. Podes escolher
«Coisas/Bananas», por exemplo, ou outra imagem de que gostes. Muda o nome desse
actor para «a roda 1». Clica no separador «Trajes» do novo actor. Se escolheste
importar um actor com mais do que um traje, remove todos os trajes com excepção
do que mais te agradar. Dá ao traje que seleccionaste um nome apropriado. Por
exemplo, «bananas».

3. Ainda no separador «Trajes», importa mais dois trajes que te agradem, de modo
a ficarmos com um total de três trajes. Podes escolher, por exemplo,
«Animais/butterfly2» e «Coisas/soccer ball». Dá nomes apropriados a esses
trajes. Podes precisar de ajustar a posição do centro dos trajes e da sua
dimensão para que o resultado seja mais parecido com uma roda de máquina caça-
níquel.

__Agora que já temos uma roda com três figuras (que é como quem diz, um actor
com três trajes), queremos que a roda gire, mostrando uma figura de cada vez
(que é como quem diz, queremos que o actor vá mudando sucessivamente de
traje).__

##PASSO 2: Fazer a roda rodar

1. Clica no separador «Guiões».

2. Clica na paleta «Eventos» e arrasta o bloco [Quando alguém clicar em A
BANDEIRA VERDE] para área dos guiões. Este bloco, quando carregarmos na bandeira
verde, dará início à execução do seu guião, ou seja, dos comandos que nele
encaixarmos.

3. Clica na paleta «Controlo». Arrasta um comando [repete para sempre,] e encaixa-o sob o bloco existente.

4. Clica na bandeira verde no canto superior direito do palco. Observa o alo
amarelo em torno do nosso novo guião. Isso significa que há comandos nesse guião
que estão a ser executado. Foi o clique na bandeira verde que desencadeou essa
execução.

5. Agora clica na paleta «Aparência» e arrasta o comando [passa para o próximo
traje], encaixando-o dentro do comando [repete para sempre,].

6. Como fazer para diminuir a velocidade a que vamos mudando de traje? Clica na
paleta «Controlo» e arrasta um comando [espera (1) s], encaixando-o dentro do
bloco [repete para sempre,], acima do comando [passa para o próximo traje].

7. Ajusta o tempo de espera (um tempo de 0,1 segundos parece adequado). __Atenção!__ O Scratch 2.0 não aceita vírgulas como separador decimal. Tens de usar um ponto! Ou seja, tens de escrever «0.1» em vez de «0,1».

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		espera (0.1) s
		passa para o próximo traje
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde.__ As figuras mudam a uma velocidade aceitável?

__Para parar, carrega no sinal de _stop_.__

###Coisas a experimentar

Ajusta o tempo do comando [espera () s]. Que valores fariam o jogo ficar muito fácil ou muito difícil?

##PASSO 3: Parando a rotação da roda

Podemos ir mudando os trajes do actor para sempre. Excelente! Mas como parar essas mudanças quando se clicar no actor?

1. Cria uma nova variável clicando primeiro na paleta «Dados» ​​e depois no
botão «Criar uma Variável». Dá o nome «o estado da máquina» à variável e deixa
seleccionada a opção «Para todos os actores». Em seguida, desmarca a caixa de
selecção junto ao bloco da nova variável que surgiu na paleta «Dados». Isso faz
com que deixe de aparecer o monitor dessa variável, que mostra no palco o seu
valor em cada instante.

2. Faz com que o valor da variável «o estado da máquina» passe a ser «parada»
sempre que alguém clicar sobre a roda. Para isso, usa o bloco [Quando alguém
clicar em ti], encaixando-lhe por baixo o comando [altera [o estado da máquina
▼] para [parada]]:

```scratch
	Quando alguém clicar em ti
	altera [o estado da máquina ▼] para [parada]
	[fim do guião]
```

3. Agora precisamos de fazer a roda parar de rodar quando a variável tiver o
valor «parada». Clica na paleta «Controlo» adiciona um comando [se &lt;>, então]
dentro do comando [repete para sempre,] contendo os blocos de espera e de
mudança de traje. Usa o operador de igualdade para verificar se a variável «o
estado da máquina» tem o valor «rodando». O resultado terá o seguinte aspecto:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	repete para sempre,
		se <(o estado da máquina) = [rodando]]>, então
			espera (0.1) s
			passa para o próximo traje
		[fim do comando «se, então»]
	[fim do guião]
```

4. Finalmente, encaixa um comando altera [[o estado da máquina ▼] para
[rodando]] logo abaixo do bloco [Quando alguém clicar em A BANDEIRA VERDE]:

```scratch
	Quando alguém clicar em A BANDEIRA VERDE
	altera [o estado da máquina ▼] para [rodando]
	repete para sempre,
		se <(o estado da máquina) = [rodando]]>, então
			espera (0.1) s
			passa para o próximo traje
		[fim do comando «se, então»]
	[fim do guião]
```

###Testa o teu projecto

__Clica na bandeira verde, espera uns instantes e, de seguida, clica sobre a roda de figuras.__ Antes de clicares na bandeira verde, as figuras vão rodando? E depois de clicares na bandeira verde? E depois de clicares sobre a roda?

__Clica novamente na bandeira verde.__ A roda pára quando pões o posicionas o
ponteiro do rato sobre ela _sem clicar_? E se clicares sobre outro qualquer
lugar do palco? E sobre outro lugar qualquer da janela do Scratch? E em algum
lugar fora da janela do Scratch?

##PASSO 4: Adicionar as duas rodas em falta

__Precisamos de adicionar duas outras rodas para podermos jogar o nosso jogo!__

1. Duplique o actor «a roda 1» clicando com o botão direito do rato sobre ele,
na área dos actores. 

2. Duplica novamente o mesmo actor para ficarmos com três rodas no palco.

3. Posiciona as rodas em linha, ao lado uma das outras, com o actor «a roda 1» à esquerda e o actor «a roda 3» à direita.

###Testa o teu projecto

__Clica na bandeira verde.__ Todas as rodas devem ir mudando de figura. Tenta fazer as rodas parar quando estão a mostrar a mesma figura!

###Coisas a experimentar

Neste momento o jogo está muito fácil, pois todas as rodas rodam à mesma
velocidade e mostram sempre as mesmas figuras, em uníssono. Que tal fazeres as
rodas rodarem para uma figura aleatória quando a bandeira verde for clicada?

__Dica:__ Tenta escolher uma figura aleatória para cada roda quando o jogo é iniciado.

__Parabéns! Terminou o jogo básico! Mas há mais coisas que podes fazer. Dá uma olhadela aos desafios!__

##DESAFIO 1: Aumenta a dificuldade do jogo

Descobre uma forma de mudares a dificuldade do jogo. Não vale limitares-te a fazer as rodas rodarem mais depressa! Tenta fazer algo mais criativo. Algumas ideias que talvez queiras experimentar:

1. Altera o número de figuras por rodas de modo a que haja mais figuras e de
modo a que o número de figuras seja diferente em cada roda.

2. Faz com que algumas rodas tenham figuras exclusivas delas.

3. Faz com que a velocidade de rotação das rodas seja diferente. Por exemplo, a
velocidade de rotação pode ir aumentando da esquerda para a direita.

4. Faz com que cada roda mude para uma figura aleatório e não para a próxima figura. Será que a máquina caça-níquel que resulta é realista? Porquê? 

__Diverte-te inventando outras alterações!__

Sempre que fizeres uma alteração, pensa se o jogo ficou mais fácil ou se ficou
mais difícil.  Será que jogo ficou demasiado fácil ou demasiado difícil?  Como
podes ajustar a dificuldade para que o jogo fique perfeito?

##DESAFIO 2: Torna o jogo mais difícil ou mais fácil ao longo do tempo

Nem todas as pessoas têm a mesma habilidade para jogar. __Como poderias fazer o jogo ajustar a sua dificuldade, dependendo do jogador?__

Uma forma de o fazer é __ajustar a velocidade de rotação das rodas, ou seja, a
velocidade de mudança dos trajes__.  Podes criar uma variável chamada «o tempo
entre figuras» para guardar o tempo a esperar entre trocas de traje.  Sempre que
o jogador ganhar uma jogada, podes reduzir um pouco o valor dessa variável, para
tornar o jogo mais difícil. Sempre que o jogador perder uma jogada, podes
aumentar um pouco o valor dessa variável, para tornar o jogo mais fácil. É claro
que só conseguirás vencer este desafio se pensares numa forma de detectar quando
as figuras nas rodas, depois do jogador as parar de rodar, forem todas iguais.
Isso é matéria para o desafio seguinte...

##DESAFIO 3: Detecta quando todas as rodas pararem na mesma figura

__O objetivo do jogo é clicar sobre as rodas para que todas parem e mostrem a
mesma figura.  Seria bom que o palco, assumindo o papel de máquina caça-níquel,
detectasse quando terminou uma jogada e, depois de inspeccionar as figuras
mostradas pelas rodas, informasse o jogador acerca do resultado dessa jogada.__

Em primeiro lugar, o palco precisa de saber quando uma jogada terminar. Isso é
fácil, pois temos uma variável global «o estado da máquina» que toma os valores
«rodando» e «parada». Podemos alterar o nosso jogo de modo a que seja o palco a
inicializar essa variável. Aliás, tal como desenvolvemos o jogo até agora, cada
uma das rodas faz essa inicialização, o que não faz assim muito sentido...
Depois de inicializar essa variável, o palco pode ficar à espera que o valor
dela passe a ser «parada».

(Aproveita o facto de estares a alterar o palco para removeres o seu único som
(«pop»), de que não precisas, e para alterar o nome do seu único cenário para
«em branco». Também pode procurar uma imagem de um mostrador de máquina caça-
níquel e usá-la como cenário!

Para saber se o jogador ganhou, o palco pode recorrer ao bloco ([o nome do traje
▼] de [a roda 1 ▼]), bem como ao mesmo bloco com «a roda 2» e «a roda 3»
seleccionados no segundo menu, para verificar se todos os nomes dos trajes das
três rodas são iguais. Claro que isto implica que não podes dar nomes iguais da
trajes diferentes, mas isso é coisa fácil de garantir. Para fazer a verificação,
podes usar um comando de selecção [se &lt;>, então senão,], o predicado de
comparação &lt;[] = []> e o predicado de conjunção &lt;[] e []>.

Deste ponto em diante, tens de decidir de que forma anuncias a vitória ou a
derrota do jogador. Podes recorrer a outro actor e difundir uma mensagem que
anuncia a vitória ou a derrota, deixando a esse actor a responsabilidade por
tornar o anúncio visível (ou audível!) ao jogador. Alternativamente, podes usar
cenários diferentes para vitórias e derrotas e mudar de cenário de forma
apropriada ao caso.

__Parabéns! Terminaste! Agora podes desfrutar do jogo!__ Não te esqueças de que
podes partilhar o teu jogo com outros Scratchadores, incluindo os teus amigos e
familiares, clicando em «Partilhar»!
