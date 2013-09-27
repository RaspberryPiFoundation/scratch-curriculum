Poziom 1

#Feliks i Herbert

__Wstęp:__
Zrobimy grę w berka z kotem __Feliksem__ i myszą __Herbertem__. Herbertem kieruje się przy pomocy myszy i trzeba uciekać przed Feliksem. Im dłużej się ucieka, tym więcej punktów się dostaje. Nie daj się złapać, bo stracisz punkty!

##KROK 1: Feliks podąża za kursorem myszy

1. Zacznij nowy projekt.
2. Kliknij na obszarze na lewo od duszka i wybierz Nowe tło, a potem kliknij W domu i wybierz tło "hall". Skasuj puste tło widoczne koło duszka.
3. Zmień nazwę duszka na Feliks.
4. Upewnij się, że Feliks obraca się tylko w lewo i prawo wciskając ten przycisk:
5. Stwórz ten skrypt:

```scratch

	kiedy kliknięto FLAGĘ

	zawsze

		idź do wskaźnik myszy

		przesuń o 10 kroków

		następny kostium

		zagraj bębenkiem 62 przez 0.3 taktów

	(koniec zawsze)
```
		

###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Czy Feliks podąża za kursorem myszy? Czy wygląda jakby chodził, kiedy się rusza? Czy porusza się z dobrą prędkością?

Zapisz swój projekt

##KROK 2: Feliks goni Herberta

__Teraz chemy, aby Feliks zaczął gonić Herberta zamiast podążać za kursorem.__

1. Stwórz następnego duszka używając przycisku z duszkiem obok "Nowy duszek", pzrejdź do kategorii Zwierzęta i wybierz Mouse1.
2. Zmień nazwę duszka na Herbert.
3. Zmień kostium, a później zmień rozmiar Herberta żeby był mniejszy od Feliksa.
Kliknij sześć razy na przycisku od zmniejszania:
4. Upewnij się, że Herbert obraca się tylko w lewo i prawo.
5. Dodaj poniższy skrypt do Herberta: 

```scratch
	
	kiedy kliknięto FLAGĘ

	zawsze
	
		idź do wskaźnik myszy
		
		ustaw w stronę Feliks
		
	(koniec zawsze)
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę.__

Czy Herbert podąża za kursorem myszy? Czy Feliks goni Herberta?

Zapisz swój projekt.

##KROK 3: Feliks daje znać, że złapał Herberta

__Chcemy, aby Feliks wiedział, kiedy złapaie Herberta i żeby dał nam znać.__

1. Zmień skrypt Feliksa na poniższy:

```scratch
	
	kiedy kliknięto FLAGĘ

	zawsze
	
		idź do wskaźnik myszy
		
		przesuń o 10 kroków

		następny kostium

		zagraj bębenkiem 62 przez 0.3 taktów
		
		jeżeli dotyka Herbert
		
			powiedz Mam cię! przez 1 s
		(koniec jeżeli)
	(koniec zawsze)
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę.__

Czy Feliks mówi, że złapał Herberta?

Zapisz swój projekt.

##KROK 4: Herbert zamienia się w ducha jak zostanie złapany

__Zamiast odzywającego się Feliksa, chcemy, aby Herbert zamieniał się w ducha jak zostanie złapany.__

1. Zamień skrypt Feliksa na poniższy, aby wysłać nową wiadomość jak Herbert zostanie złapany.

```scratch
	
	kiedy kliknięto FLAGĘ

	zawsze
	
		idź do wskaźnik myszy
		
		przesuń o 10 kroków

		następny kostium

		zagraj bębenkiem 62 przez 0.3 taktów
		
		jeżeli dotyka Herbert
		
			nadaj Złapany!
			
			zagraj bębenkiem 58 przez 0.2 taktów
			
			czekaj 1 s
		(koniec jeżeli)
	(koniec zawsze)
```
2. Import a new costume into Herbert from fantasy/ghost2-a.
3. Edit the costume to make it smaller.
Six clicks on the shrink button should do.
4. Change the names of Herbert’s
costumes so the mouse costume is
called ‘alive’ and the ghost costume is called ‘dead’.
5. Create a new script for Herbert to turn him into a ghost:

```scratch
	
	when I receive caught
	switch to costume dead
	wait 0.5 secs
	switch to costume alive
```
	
###Test Your Project
__Click the green flag.__

Does Herbert turn into a ghost when he’s caught?
Does Felix play the right sounds at the right time?
Does Felix still stay still for long enough for Herbert to get away

Save your project

##STEP 5: Keep Score

__Let’s add a score so we know how well we do at keeping Herbert alive.
We’ll start the score at zero and increase it by one every second. If Felix catches Herbert, we’ll reduce the score by one hundred.__

1. Make a variable, for all sprites, called Score. Click on Variables in the top menu, make a variable and name it score
2. On the stage, create these two scripts

```scratch
	
	when FLAG clicked
	set score to 0
	forever
		change score by 1
		wait 1 secs
	(end forever)
	
	when I receive caught
	change score by -100
```
	
###Test Your Project
__Click the green flag.__

Does the score go up by one every second?
Does the score go down by one hundred when Herbert is caught?
What happens when Herbert is caught before score reaches one hundred? Does the score go back to zero when you start a new game?

Save your project

__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar
