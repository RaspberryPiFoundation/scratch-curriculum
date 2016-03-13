---
title: Clone Wars
level: Scratch 2
language: pl-PL
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
beta: true
...

## Projekt stworzony przez społeczność { .challenge .pdf-hidden }
Ten projekt powstał przy współpracy z Erikiem. Jeśli także chcesz zamieścić swój projekt [skontaktuj się z nami na Githubie](https://github.com/CodeClub).

# Wstęp { .intro }

Wykonując ten projekt nauczysz się, jak stworzyć grę, w której musisz uratować Ziemię przed potworami z kosmosu.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/46018140/?autostart=false" frameborder="0"></iframe>
  <img src="invaders-final.png">
</div>

# Krok 1: Budowanie statku kosmicznego {.activity}

Zbudujmy statek kosmiczny, który będzie bronił Ziemi!

## Zadania do wykonania {.check}

+ Utwórz w Scratchu nowy projekt i usuń duszka-kota tak, aby projekt był pusty. Możesz skorzystać ze Scratcha w wersji online, który znajduje się tutaj: <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Do projektu dodaj tło 'stars' (gwiazdy) i duszka 'Spaceship' (statek kosmiczny). Zmiejsz statek kosmiczny i przesuń go na dół sceny.

	![screenshot](invaders-sprites.png)

+ Dodaj kod, który przesunie statek w lewo, kiedy wciśniesz strzałkę w lewo. Będziesz do tego potrzebował takich bloków:

	```blocks
		when flag clicked
		forever
			if <key [left arrow v] pressed?> then
				change x by (-4)
			end
		end
	```

+ Dodaj kod, który przesunie statek w prawo, kiedy wciśniesz strzałkę w prawo.

+ Przetestuj swój projekt i sprawdź czy statek przesuwa się kiedy wciskasz strzałki na klawiaturze.

## Zapisz swój projekt {.save}

# Krok 2: Błyskawice {.activity}

Dodajmy statkowi kosmicznemu możliwość strzelania błyskawicami!

## Zadania do wykonania {.check}

+ Z biblioteki Scratcha dodaj duszka 'Lightning' (błyskawica). Kliknij na kostium duszka i obróc go do góry nogami.

	![screenshot](invaders-lightning.png)

+ Na początku gry błyskawica powinna być ukryta. Pokażemy ją dopiero wtedy, kiedy statek kosmiczny wystrzeli ze swoich laserowych działek.

	```blocks
		when flag clicked
		hide
	```

+ Dodaj poniższy kod **do statku kosmicznego**, by utworzyć nową błyskawicę za każdym razem, kiedy wciśnięta zostanie spacja.

	```blocks
		when flag clicked
		forever
			if <key [space v] pressed?> then
				create clone of [Lightning v]
			end
		end
	```

+ Kiedy nowy klon zostanie stworzony powinien ustawić się w tym miejscu, gdzie znajduje się statek kosmiczny. Następnie powinien poruszać się w górę sceny dopóki nie dotknie krawędzi. Dodaj poniższy kod **do błyskawicy**:

	```blocks
		when I start as a clone
		go to [Spaceship v]
		show
		repeat until <touching [edge v] ?>
			change y by (10)
		end
		delete this clone
	```

  Uwaga: ustawiamy nowy klon błyskawicy na pozycję statku kosmicznego kiedy jeszcze błyskawica jest ukryta, przed jej pokazaniem. Dzięki temu gra będzie lepiej wyglądać.

+ Przetestuj swoją błyskawicę naciskając spację.

## Zapisz swój projekt {.save}

## Wyzwanie: Naprawianie błyskawicy {.challenge}
Co się dzieje, kiedy trzymasz wciśniętą spację? Użyj bloku `czekaj` {.blockcontrol}, aby to naprawić.

## Zapisz swój projekt {.save}

# Krok 3: Latające kosmo-hipcie { .activity }

Dodajmy teraz mnóstwo latających hipopotamów, które będą próbowały zniszczyć statek kosmiczny.

## Zadania do wykonania {.check}

+ Stwórz nowego duszka wykorzystując 'Hippo1' z biblioteki Scracha.

	![screenshot](invaders-hippo.png)

+ Ustaw mu styl obrotów tak, aby obracał się tylko w prawo i w lewo. Dodaj mu też poniższy kod, aby ukryć go na początku gry:

	```blocks
		when flag clicked
		hide
	```

+ Stwórz nową zmienną tylko dla tego duszka i nazwij ją `prędkość` {.blockdata}.

	![screenshot](invaders-var.png)

  Jeśli udało ci się to zrobić poprawnie twoja zmienna będzie miała nazwę duszka obok swojej nazwy, tak jak tutaj:

	![screenshot](invaders-var-test.png)

+ Poniższy kod utworzy nowego kosmo-hipcia co kilka sekund. Dodaj ten kod **do sceny**:

	```blocks
		when flag clicked
		forever
			wait (pick random (2) to (4)) secs
			create clone of [Hippo1 v]
		end
	```

+ Niech każdy nowy klon kosmo-hipcia na początku porusza się po scenie (z losową prędkością) tak długo, aż nie zostanie zestrzelony przez błyskawicę. Dodaj poniższy kod **do kosmo-hipcia**:

	```blocks
		when I start as a clone
		set [speed v] to (pick random (2) to (4))
		go to x: (pick random (-220) to (220)) y: (150)
		show
		repeat until <touching [lightning v] ?>
			move (speed) steps
			turn right (pick random (-10) to (10)) degrees
			if on edge, bounce
		end
		delete this clone
	```

+ Przetestuj kod kosmo-hipcia. Co kilka sekund powinien pokazywać się nowy klon kosmo-hipcia, a każdy z nich powinien posuszać się ze swoją prędkością.

	![screenshot](invaders-hippo-test.png)

+ Przetestuj działka laserowe. Czy trafiony błyskawicą kosmo-hipcio znika?

+ Kiedy kosmo-hipcio dotknie twojego statku kosmicznego, statek powinien eksplodować! Aby tak zrobić, najpierw musimy zmienić statek w taki sposób, aby miał dwa kostiumy: "normalny" i "trafiony".

	![screenshot](invaders-spaceship-costumes.png)

  Kostium "trafiony" można wykonać importując z biblioteki Scratcha obrazek "sun" (słońce), a następnie używając narzędzia "Wypełnij kształt", aby zmienić jego kolor.

	![screenshot](invaders-sun.png)

+ Dodaj ten kod do swojego statku, aby zmienił kostium kiedy tylko zostanie uderzony przez kosmo-hipcia:

	```blocks
		when flag clicked
		forever
			switch costume to [normal v]
			wait until <touching [Hippo1 v]>?
			switch costume to [hit v]
			broadcast [hit v]
			wait (1) secs
		end
	```

+ Czy zauważyłeś, że wysyłasz wiadomość "trafiony" w kodzie powyżej? Możesz użyć tej wiadomości, aby ukryć wszystkie kosmo-hipcie, kiedy statek zostanie trafiony przez jednego z nich.

	Dodaj poniższy kod do kosmo-hipcia:

	```blocks
		when I receive [hit v]
		delete this clone
	```

+ Przetestuj ten kod - uruchom nową grę i pozwól, aby uderzył cię kosmo-hipcio.

	![screenshot](invaders-hippo-collide.png)

## Zapisz swój projekt {.save}

## Wyzwanie: Życia i punkty {.challenge}
Czy potrafisz dodać `życia` {.blockdata}, `punkty` {.blockdata}, albo nawet `najlepszy wynik` {.blockdata} do swojej gry? Pomocy szukaj w projekcie "Catch the Dots".

## Zapisz swój projekt {.save}

# Step 4: Fruit Bats! { .activity }

Let's make a fruit bat that throws oranges at your spaceship.

## Zadania do wykonania {.check}

+ Firstly, make a new bat sprite that will `move` {.blockmotion} across the top of the stage `forever` {.blockcontrol}. Remember to test out your code.

	![screenshot](invaders-bat.png)

+ If you look at the bat's costumes, you'll see that it already has 2:

	![screenshot](invaders-bat-costume.png)

	Use the `next costume` {.blocklooks} block to make the bat flap its wings as it moves.

+ Create a new 'Orange' sprite from the Scratch library

	![screenshot](invaders-orange.png)


+ Add code to your bat, so that it creates a new orange clone every few seconds.

	```blocks
		when flag clicked
		forever
			wait (pick random (5) to (10)) secs
			create clone of [Orange v]
		end
	```

+ Click on your orange sprite and add this code to make each orange clone drop down the stage from the bat towards the spaceship:

	```blocks
		when flag clicked
		hide

		when I start as a clone
		go to [Bat1 v]
		show
		repeat until <touching [edge v]?
			change y by (-4)
		end
		delete this clone

		when I receive [hit v]
		delete this clone
	```

+ In your spaceship sprite, you'll need to modify your code so that you are hit if you touch a hippo or an orange:

	```blocks
		wait until < <touching [Hippo1 v]?> or <touching [Orange v]?>>
	```

+ Test your game. What happens if you get hit by a falling orange?

## Zapisz swój projekt {.save}

# Step 5: Game over { .activity }

Let's add a 'game over' message at the end of the game.

## Zadania do wykonania {.check}

+ If you haven't already, create a new variable called `lives` {.blockdata}. Your spaceship should start with 3 lives and lose a life whenever it collides with an enemy. Your game should also stop when you run out of lives. If you need help, you can use the 'Catch the Dots' project to help you.

+ Draw a new sprite called 'Game Over', using the text tool.

	![screenshot](invaders-game-over.png)

+ On your stage, broadcast a `game over` {.blockevents} message just before the game ends.

	```blocks
		broadcast [game over v] and wait
	```

+ Add this code to your 'Game Over' sprite, so that the message shows at the end of the game:

	```blocks
		when flag clicked
		hide

		when I receive [game over v]
		show
	```

	Because you've used a `broadcast [game over] and wait` {.blockevents} block on your stage, it will wait for the 'Game Over' sprite to be displayed before ending the game.

+ Test your game. How many points can you score? Can you think of ways to improve your game if it is too easy or too hard?

## Zapisz swój projekt {.save}

## Challenge: Improve your game {.challenge}
What improvements can you make to your game? Here are some ideas:
+ Add health packs that you can collect to gain extra lives;

![screenshot](invaders-aid.png)

+ Add floating rocks that your spaceship must avoid;

![screenshot](invaders-rocks.png)

+ Make more enemies appear when your score gets to 100.

```blocks
	wait until <(score) = [100]>
```

## Zapisz swój projekt {.save}
