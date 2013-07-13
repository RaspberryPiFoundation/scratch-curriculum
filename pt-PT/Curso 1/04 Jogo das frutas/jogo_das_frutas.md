Nível 2 

#Jogo das frutas (máquina caça-níquel)

__Introdução:__

Este jogo simula uma máquina caça-níquel (ou _slot machine_) com três rodas de
figuras. Essas rodas vão rodando, variando a figura de cada uma dessas rodas que
é visível no mostrador da máquina. Para ganhar o jogo, o jogador tem de
interromper a rotação das rodas quando as figuras visíveis forem todas iguais.

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
trajes.

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

Ajuste o tempo do comando __espere__. Quais valores fariam o jogo ficar muito fácil ou muito difícil?

## PASSO 3: Fazendo parar quando clicado

Excelente! Nós podemos fazer os trajes do objeto mudarem sem parar, mas como vamos fazer para que ele pare quando clicado?

1. Crie uma nova variável clicando Variáveis ​​e __criar uma variável__. 
Dê o nome de __parado__ e deixe marcado a opção __para todos os objetos__, em seguida, desmarque a caixa ao lado de __parado__ 
na área de comandos para que ela não seja exibida no palco.
2. Mude a variável __parado__ para __1__ (um) quando alguém clicar sobre a imagem. Para isso utilize o comando
__quando Sprite1 clicado__ e o comando __mude parado para__. 
3. Agora precisamos fazer a imagem parar de mudar quando a variável __parado__ é igual a 1. 
Clique controle e substitua o comando __sempre__ por um comando  __sempre se__ 
e use um novo operador igual (=) para testar se __parado__ é igual a 0
4. Finalmente, encaixe um comando __mude parado para 1__ logo abaixo de __quando bandeira clicada__

### Teste o projeto

__Clique na bandeira verde, espere por um momento, em seguida, clique sobre o objeto.__ 

Os trajes mudam antes de você clicar?
 
Ele para quando você clica sobre ele?


__Clique novamente na bandeira verde__ 

Ele para quando você posiciona o ponteiro do mouse sobre ele sem clicar? 

Ele para quando você clica em outro lugar do palco? Em algum outro lugar da janela do Scratch? Em algum lugar fora da janela do Scratch?

Salve seu projeto

## Passo 4: Criando os outros objetos

__Precisamos adicionar outros objetos para fazer o nosso jogo!__

1. Duplique o objeto 1 (sprite1) clicando com o botão direito sobre ele, no canto inferior direito.
2. Duplique-o novamente para termos três objetos na tela.
3. Posicione os objetos para que eles fiquem em linha. Redimensione se necessário.

### Teste o projeto
__Clique na bandeira verde.__ 

Todos os objetos devem mudar de traje. Tente fazê-los parar na mesma imagem!

Salve seu projeto

### Sugestões

No Início todos os objetos mostram o mesmo traje ao mesmo tempo. 
Que tal você fazer os objetos mudarem para um traje aleatório quando a bandeira verde for clicado?
Dica: tente escolher um traje aleatório para cada objeto quando o jogo é iniciado.

__Parabéns, você terminou o jogo básico. Há mais coisas que você pode fazer. Dê uma olhada nestes desafios!__


## Desafio 1: Aumente a dificuldade do jogo

Mude a dificuldade do jogo de alguma maneira. 
Apenas fazer os imagens mudarem mais rápido não vale. 
Tente fazer algo mais criativo. 
Algumas idéias que você pode experimentar:

1. Altere o número de trajes de cada objeto.
2. Faça com que alguns objetos tenham trajes exclusivos.
3. Faça com que o intervale entre as mudanças de traje seja diferente.
4. Faça com que cada objeto mude para um traje aleatório e não para o próximo traje. 

__Divirta-se com as suas próprias idias!__

Toda vez que você faz uma alteração, pense se o o jogo ficou mais fácil ou mais difícil. 
O jogo é muito fácil ou muito difícil? 
Como você pode ajustar a dificuldade para que fique melhor?


## Desafio 2: Faça o jogo ficar mais difícil ou mais fácil ao longo do tempo

Nem todas as pessoas tem a mesma habilidade para jogar. __Como você poderia fazer o jogo ajustar sua dificuldade, dependendo do jogador?__

Uma maneira é __ajustar a velocidade da mudança de trajes__. 
Você pode criar uma variável chamada __intervalo__, para representar a duração do comando __espere__ de cada objeto. 
Se o jogador ganha a rodada, a variável intervalo pode ser reduzida um pouco (para tornar o jogo mais difícil). 
Se o jogador perde a rodada, o intervalo pode ser aumentado um pouco (para tornar o jogo mais fácil).

## Desafio 3: Detecte quando todos os objetos pararem no mesmo traje

__O objetivo do jogo é clicar sobre os objetos para que eles parem mostrando o mesmo traje. 
Seria bom se o palco detectasse quando você terminou de jogar e, em seguida, diga se você ganhou ou perdeu, 
verificando se cada objeto tem o mesmo traje.__

Em primeiro lugar, o palco precisa saber quando o jogo tiver acabado. 
Cada vez que alguém clica em um dos objetos, o palco deve verificar se todos os objetos já foram clicados. 
Modifique o comando __quando clicado__ de cada objeto para que ele anuncie uma nova mensagem, chamada por exemplo __verifica fim__.

O palco pode ouvir esta mensagem e verificar se as variáveis __parado__ dos três objetos valem 1 para saber se o jogo acabou. 
Para isso, encaixe um bloco __posição x de__ e mude "posição x" para "parado". 
Se a variável __parado__ dos três tem valor de 1, sabemos que o jogo acabou e nós podemos verificar se o jogador ganhou.

Para fazer isso, podemos usar a mesma tipo de bloco __posição x de__, mas em vez de olhar a variável __parado__, 
iremos olhar a variável traje # e assim podemos comparar se Objeto1 tem o mesmo traje que Objeto2, e se Objeto2 tem o mesmo traje que Objeto3.

Para fazer isso, você precisa de um bloco __se__ para verificar cada variável,
 e dentro dele um bloco __se ... senão__ para ver se o jogador ganhou ou perdeu, comparando cada 
traje.

Deste ponto em diante, você pode anunciar o resultado do jogo usando um bloco __anuncie__ e receber esta mensagem em um outro objeto. 



__Parabéns você terminou, agora você pode desfrutar do jogo!__
Não esqueça que você pode compartilhar o seu jogo com todos os seus amigos e familiares clicando em __Compartilhar__ no menu!
