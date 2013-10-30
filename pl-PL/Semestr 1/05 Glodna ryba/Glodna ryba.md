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
__Spróbuj złapać krewetkę – czy widzisz jakieś problemy?__ Zauważ, że krewetka znika bez względu na to, z której strony dotknie rybę. Poza tym, jeżeli ryba się nie rusza, to po 3 sekudnach może od razu zjeść krewetkę – to jest trochę niefajne!

2. Co możemy zrobić, aby upewnić się, że krewetka znika tylko wtedy, gdy ryba dotknie jej paszczą? Możemy skorzystać z czujnika koloru i sprawdzać, czy krewetka dotyka niebieskich zębów ryby! Aby to zrobić, zamień blok 'dotyka Głodna Ryba' na 'dotyka koloru', kliknij kwadracik z kolorem, a gdy kursor myszy się zmieni, kliknij na zębach ryby.
3. Następnie możemy sprawić, aby krewetka przesuwała się w losowe miejsce na ekranie przed ponownym pojawieniem. Możemy użyć do tego bloku 'idź do' i użyć losowych wartości dla x i y. 

```scratch

	kiedy kliknięto FLAGĘ

	zawsze

		przesuń o 2 kroków

		obróć o losuj liczbę pomiędzy -20 a 20 stopni

		jeżeli na brzegu, odbij się
		
		jeżeli dotyka koloru []
			
			ukryj
			
			czekaj 3 s
			
			idź do x: losuj liczbę pomiędzy -220 a 220 y: losuj liczbę pomiędzy -170 a 170
			
			pokaż
		
		(koniec jeżeli)
		
	(koniec zawsze)
	
```
###Przetestuj swój projekt
Spróbuj złapać krewetkę jeszcze raz - czy znika ona tylko wtedy, kiedy dotknie zębów ryby? I czy pojawia się w losowym miejscu na ekranie zamiast od razu tam, gdzie została zjedzona?

4. Ryba musi wiedzieć, kiedy zjadła krewetkę, aby mogła wydać dźwięk i zmienić skórę. Aby to zrobić, wpierw musimy nadać sygnał, że krewetka została zjedzona.

```scratch

	kiedy kliknięto FLAGĘ

	zawsze

		przesuń o 2 kroków

		obróć o losuj liczbę pomiędzy -20 a 20 stopni

		jeżeli na brzegu, odbij się
		
		jeżeli dotyka koloru []
		
			nadaj masz mnie
			
			ukryj
			
			czekaj 3 s
			
			idź do x: losuj liczbę pomiędzy -220 a 220 y: losuj liczbę pomiędzy -170 a 170
			
			pokaż
		
		(koniec jeżeli)
		
	(koniec zawsze)
	
```

__Teraz chcemy, aby ryba odpowiedziała na to głośnym zamknięciem paszczy.__

5. Upewnij się, że Głodna Ryba ma dodane oba kostiumy i dodaj plik z dźwiękiem z katalogu Zasoby (ewentualnie możesz nagrać swój własny dźwięk lub użyć Slurp z katalogu Human).
6. Następnie dodaj skrypt do Głodnej Ryby, który odpowiada na wiadomość nadaną przez jej ofiarę. Skrypt powinien zagrać odgłos jedzenia i zamienić kostium ryby na ten z zamkniętą paszczą, a następnie poczekać chwilę i wrócić do pierwszego kostiumu.

```scratch

	kiedy otrzymam masz mnie
	
	zagraj dźwięk Slurp
	
	powtórz 2 razy
	
		zamień kostium na ryba-paszcza-zamknieta
		
		czekaj 0.5 s
		
		zamień kostium na ryba-paszcza-otwarta

	(koniec powtórz)
	
```

__Skoro nasz Głodna Ryba jest gotowa jeść, wypełnijmy ocean jedzeniem. Kliknij na krewetce prawym przyciskiem myszy i duplikuj ją kilka razy.__

###Przetestuj swój projekt
Kliknij zieolną flagę.
Czy Głodna Ryba zjada swoje ofiary? Czy potrafi zjeść każdą krewetkę?

Zapisz swój projekt

###Rzeczy do przemyślenia
Dlaczego musimy dodać blok 'pokaż' na początku skryptu każdej krewetki? Pomyśl, co by się stało, gdyby gra została zatrzymana zanim zjedzona krewetka ponownie pojawi się na ekranie. Co by się stało po uruchomieniu gry?

__Brawo! Udało Ci się skończyć podstawową wersję gry. Jest jeszcze kilka rzeczy, które możesz zmienić w grze. Pora na wyzwanie?__


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
