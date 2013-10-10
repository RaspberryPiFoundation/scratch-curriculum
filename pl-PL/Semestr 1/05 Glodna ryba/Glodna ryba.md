Poziom 2

#Głodna ryba

__Wstęp:__
Zrobimy grę w karmienie ryb! Będziesz kierować dużą głodną rybą pływającą po morzu, aby udało jej się zjeść wszystkie przynęty.

##KROK 1: Stwórz duszka, który zmienia kostiumy
__Dodajmy rybę, która pływa po morzu!__

1. Zacznij nowy projekt w Scratchu.
2. Zaznacz Scenę, a następnie przejdź do karty z ustawieniami tła. Zaimportuj tło "underwater" z katalogu Nature. Usuń tło1.
3. Zmień nazwę duszka z Duszek1 na Głodna Ryba.
4. Zaimportuj oba kostiumy Głodnej Ryby z katalogu Zasoby i skasuj istniejący kostium1 i kostium2.
5. Wciśnij przycisk nad list kostiumów, aby upewnić się, że duszek może obracać się tylko w prawo i lewo.
6. Dodaj skrypt, który każe rybie podążąć za kursorem myszy:

```scratch

	kiedy kliknięto FLAGĘ
	
	zawsze
			
		ustaw w stronę wskaźnik myszy
		
		przesuń o 3 kroków
		
	(koniec zawsze)
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę.__
Poruszaj kursorem myszy po morzu. Czy ryba pływa za nim?
Co się dzieje, jeżeli nie ruszasz kursorem i ryba go łapie? Jak to wygląda? Dlaczego tak się dzieje?

7. Możesz zapobiec takiemu motaniu się ryby, jeżeli każesz jej ruszać się tylko wtedy, kiedy nie jest za blisko kursora (w sekcji Czujniki znajdziesz blok _odległość do_).

```scratch

	kiedy kliknięto FLAGĘ
	
	zawsze, jeżeli odległość do wskaźnik myszy > 10
	
		ustaw w stronę wskaźnik myszy
		
		przesuń o 3 kroków
		
	(koniec zawsze)
```


###Przetestuj swój projekt

Zapisz swój projekt.

###Rzeczy do spróbowania
Jeżeli chcesz, możesz zmienić liczby w skrypcie. W jaki sposób zmienia to sposób poruszania się Głodnej Ryby? Zmień odległość na jakiąś dużą liczbę (np. 100) albo jakąś bardzo małą (np. 1). Zmień ilość kroków na coś dużego (np. 20) lub małego (np. 1 lub nawet 0). Co się dzieje?


##KROK 2: Dodaj krewetkę

1. Stwórz nowego duszka korzystając z kostiumu lobster1 z katalogu Animals.
2. Zmiejsz nowego duszka (narzędzie do zmniejszania znajduje się nad Sceną).
3. Dodaj skrypt, który kieruje pływającą krewetką. Chcemy, aby ruszała się losowo, więc byłoby dobrze, aby najpierw ruszała się trochę do przodu, a potem skręciła albo w lewo, albo w prawo, a potem zaczęła się ruszać od nowa. 

```scratch

	kiedy kliknięto FLAGĘ
	
	zawsze
	
		przesuń o 2 kroków
		
		obróć o losuj liczbę pomiędzy -20 a 20 stopni
		
		jeżeli na brzegu, odbij się
		
	(koniec zawsze)
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę__ i popatrz, jak krewetka porusza się po ekranie. Czy pływa tak jak trzeba? Czy wygląda to realistycznie?

__Obecnie ryba i krewetka nie interesują się sobą. Zajmiemy się tym w następnym kroku.__

Zapisz swój projekt

###Rzeczy do spróbowania

* Zmień liczby w bloku __losuj liczbę pomiędzy__ oraz odległość, o jaką porusza się krewetka. W jaki sposób te zmiany wpływają na sposób poruszania się?
* Co robi blok __jeżeli na brzegu, odbij się__? Co się stanie, jak go nie będzie? Usuń go i sprawdź.

##KROK 3: Głodna ryba łapie krewetkę

__Chcemy, aby ryba zjadła swoją ofiarę!__ Jak tylko ryba złapie żyjątko, dwie rzeczy muszą mieć miejsce:
* Ryba musi zamknąć paszczę z głośnym "mlask!"
* Krewetka musi zniknąć i pojawić się chwilę później gdzie indziej

1. Na początek sprawmy, aby krewetka znikała, jak tyko dotknie ryby i po 3 sekudnach pojawiała się gdzie indziej. Użyjemy bloku __dotyka__, aby sprawdzić, czy krewetka jest w kontakcie z rybą.

```scratch


	kiedy kliknięto FLAGĘ

	zawsze

		przesuń o 2 kroków
	
		obróć o losuj liczbę pomiędzy -20 a 20 stopni
	
		jeżeli na brzegu, odbij się
		
		jeżeli dotyka Głodna Ryba
			
			ukryj
			
			czekaj 3 s
			
			pokaż
		
		(koniec jeżeli)
		
	(koniec zawsze)
```

###Przetestuj swój projekt
__Spróbuj złapać krewetkę – czy widzisz jakieś problemy?__ Zauważ, że krewetka znika bez względu na to, z której strony dotknie ryę. Poza tym, jeżeli ryba się nie rusza, to po 3 sekudnach może od razu zjeść krewetkę – to jest trochę niefajne!

2. How could we make sure the prey only disappears if it is touching the hungry fish’s mouth? Well, we could use the touching color block, and see if it is touching the fish’s blue teeth. To do this, replace the touching block with a
touching color block in your script, click on the color in the block and then click again on the fish’s teeth.
3. Next we can make the prey move to a random point on the screen before reappearing using a go to
block, and giving it a random
value for x and y.

```scratch

	when FLAG clicked
	forever		
		move 2 steps
		turn pick random -20 to 20 degrees
		if on edge, bounce
		if touching colour []?
			hide
			wait 3 secs
			go to x:random -220 to 220 y: pick random -170 to 170
			show
		(end if)
	(end forever)
```
###Test your project

Try the game again – does the prey only vanish when it touches the fish’s mouth? And does it re-appear in a random point on the screen instead of where it was eaten?

4. The fish needs to know when it has eaten something so it can play a sound and change its skin. To do this, we can have the prey broadcast the fact that it’s been eaten before vanishing.

```scratch

	when FLAG clicked
	forever		
		move 2 steps
		turn pick random -20 to 20 degrees
		if on edge, bounce
		if touching colour []?
			broadcast got me
			hide
			wait 3 secs
			go to x:random -220 to 220 y: pick random -170 to 170
			show
		(end if)
	(end forever)
```
__Now we want the fish to respond
to this message by making a “chomp” sound and snapping its jaws.__

5. Add the resources/mouth-closed costume and the resources/chomp sound to the Hungry Fish sprite.
6. Then, add a new script to the Hungry Fish to respond to the message broadcast by the prey. This script should make the fish play the 'chomp' sound and switch to the mouth-closed costume, wait briefly and then switch back.

```scratch

	when I receive got me
	play sound chomp
	repeat 2
		switch to costume mouth-closed
		wait 0.5 secs
		switch to costume hungry-fish
	(end repeat)
```

__Now our Hungry Fish is ready to eat, let’s fill the ocean with prey. Right-click on the prey sprite and click “duplicate” several times.__

###Test Your Project
Click the green flag.
Does the Hungry Fish eat the prey? Does it eat each of the different prey?

Save your project

###Things to think about
Why do we need to add the show block to the start of the prey’s script? Think about what would happen if the prey is eaten, then the game is stopped before it reappears. What would happen if the game was restarted then?

__Well done you’ve finished the basic game. There are more things you can do to your game though. Are you ready for a challenge?__


##Challenge 1: Make the prey move differently

At the moment, all the prey move in the same way. __Can you make one of them
move differently?__
__Hint:__ Don’t spend too long on this bit without looking at the other activities in this
project.

__Pick one of the prey to experiment on.__ If they have the same costumes, make it a different colour with the __set color effect block__. That way, you can tell it apart from the rest of the prey.

Make this prey move slower than the others. __Hint:__ Look at the move (2) steps block.


###Test Your Project
Does the prey move slower? Does this make the game better?
If you can do that, __try to making one of fish move quicker than the others.__


Does the prey still move in a sensible way? Do these changes make the game better?
__Hint:__ If your prey swims around in circles, check the values of the pick random block in the turn block.

How about you make each of the prey behave differently, using different combinations of these changes?

Do any of these changes make the game better? Do they make the game more interesting, more fun, harder, or easier? Are any of those “better”?

Save your project

##Challenge 2: Make the prey avoid the hungry fish

The prey in this game are really stupid! They just swim around randomly until they’re eaten. Real fish swim away from predators. __Let’s make one of the prey swim away from the Hungry Fish.__

There’s no block in Scratch that tells you the direction that another sprite is in. But you can make one sprite point towards another, then make it turn around to face away. The blocks you need are in the __Motion__ palette.

Using that idea, __make one of the prey always point away from the Hungry Fish.__ You might want to make it wiggle as it swims away.

###Test Your Project
Does this make the fish harder to catch? Does it make the game better?

Save your project

##Challenge 3: Add a score
It’s not enough just to eat fish. How do you know you’re better at the game than your
friends? __You need a way to keep score so lets add a score board.__ Look at the __Keep Score scratch card__ for an idea of how to do it. 

Where should you put the block that changes the score?

Make sure the score goes back to zero at the start of the game. Where should you put that block?

###Test Your Project
Does the score go to zero at the start of the game? Does it go up every time you eat prey?

Save your project

##Challenge 4: Add a countdown

__Give yourself a time limit in the game.__ How many fish can you eat in thirty
seconds?

Look at the __Timer scratch card__ for how to add a timer to the game. Start with the game lasting thirty seconds.

###Test Your Project
Does the timer start at 30?

Does it go down at the right speed?

Can you catch prey while the timer is going?

Does the game stop when the timer reaches zero?

Save your project

##Challenge 5: Add a bonus score
Award a large bonus score if you can eat all three fish at the same time. How can
you tell how many fish have been eaten?
__Hint:__ One way to do this __uses a variable to count how many prey are swimming around.__

Save your project

##Challenge 6: Change the game: keep a prey alive! Sometimes, you can have great new ideas by taking an existing idea and doing the opposite.

__Modify the game so that, instead of you controlling a fish that tries to eat the others, you control one prey in a sea with lots of Hungry Fish.__ How long can you last before you’re eaten?

Save your project

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!T
