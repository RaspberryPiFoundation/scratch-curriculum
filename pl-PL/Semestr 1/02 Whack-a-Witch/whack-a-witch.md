Poziom 1

#Whack-a-Witch

__Wstęp:__
Ten projekt jest jak popularna gra zwana Whack-A-Mole: zdobywasz punkty uderzając wiedźmy, które pojawiają się na ekranie. Celem gry jest zdobycie jak największej ilości punktów w ciągu 30 sekund.

##KROK 1: Stwórz latającą wiedźmę

1. __Zacznij nowy projekt w Scratchu.__
2. __Usuń duszka kota__ i zastąp tło lasem (__woods__) z katalogu __Nature__.
3. Użyj przycisku "wybierz nowego duszka z pliku", aby dodać wiedźmę do projektu (znajdź kostium __witch1__ w katalogu __Fantasy__).

__Teraz chcemy sprawić, aby wiedźma zaczęła się ruszać__

4. Dodaj Zmienną tylko dla tego duszka i nazwij ją "prędkość".
Nowa zmienna powinna pojawić się na __Scenie__ jako "__Duszek1 prędkość".
Jeżeli widzisz tam tylko "prędkość", skasuj zmienną i stwórz nową jeszcze raz tylko dla tego jednego duszka. 
Odznacz "prędkość" w __panelu Zmiennych__, aby nie było widać tej zmiennej na Scenie.
Zmienna od prędkości będzie kontrolować jak szybko wiedźma się rusza. Korzystamy ze zmiennej, aby móc zmieniać prędkość wiedźmy wraz z postępami w grze.
5. Chcemy, aby wiedźma zaczęła się ruszać po rozpoczęciu gry. __Stwórz dla niej poniższy skrypt__:

```scratch

	kiedy kliknięto FLAGĘ

	ustaw prędkość na 5

	zawsze

		przesuń o prędkość kroków

	(koniec zawsze)
```
		
###Przetestuj swój projekt
__Kliknij zieloną flagę__ i zobacz, co robi wiedźma. Dlaczego utyka na brzegu ekranu?

6. Aby wiedźma nie utykała, musimy sprawić, że będzie zawracać za każdym razem, gdy doleci do brzegu ekranu. Poniżej bloku "przesuń o prędkość kroków" dodaj blok "jeżeli na brzegu, odbij się".


```scratch

	kiedy kliknięto FLAGĘ
	
	ustaw prędkość na 5

	zawsze

		przesuń o prędkość kroków

		jeżeli na brzegu, odbij się

	(koniec zawsze)
```

7. Aby wiedźma nie obracała się do góry nogami, wybierz ruszanie tylko w prawo i lewo w ustawieniach tego duszka. 

###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Czy wiedźma lata od brzegu do brzegu ekranu?

Zapisz swój projekt

###Rzeczy do spróbowania
__Spróbuj zmieniać wartość zmiennej prędkości, aby sprawić, żeby wiedźma latała szybciej i wolniej.__

__Co zrobić, aby wiedźma była coraz szybsza im dłużej lata?__
(To jest trochę tricky, więc nie martw się, jeżeli nie widisz jeszcze rozwiązania. Dostaniesz więcej wskazówek podczas dalszej pracy nad projektem.)

##KROK 2: Spraw, aby wiedźma pojawiała się i znikała losowo

Aby gra była ciekawsza, chcemy aby wiedźma pojawiała się i znikała losow. Będzie nam do tego potrzebny kolejny skrypt, który działa w tym samym czasie co ten odpowiedzialny za poruszanie wiedźmą. Nowy skrypt powinien chować wiedźmę w losowych momentach, pokazywać ją znowu po jakimś czasie i powtarzać te dwie akcje w nieskończoność (albo do końca gry).

__Stwórz poniższy skrypt dla wiedźmy:__

```scratch

	kiedy kliknięto FLAGĘ

	zawsze

		ukryj

		czekaj losuj liczbę pomiędzy 2 a 5 s

		pokaż

		czekaj losuj liczbę pomiędzy 3 a 5 s

	(koniec zawsze)
```
###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Czy wiedźma lata od brzegu do brzegu ekranu oraz pojawia się i nizka w losowych momentach?

Zapisz swój projekt

###Rzeczy do spróbowania
__Spróbuj zmieniać przedział liczb losowych. Co się dzieje, jeżeli wybierzesz bardzo duże albo bardzo małe liczby?__
Czy podpowiada ci to już jak sprawić, aby wiedźma latała szybciej im dłużej się gra?)

##KROK 3: Spraw, aby wiedźma znikała, gdy się na nią kliknie

Aby zamienić ten projekt w grę, musimy dać graczom coś do robienia: muszą klikać wiedźmę, aby zniknęła. Chemy, aby po kliknięciu było słuchać dźwięk i aby wiedźma znikała z ekranu.

1. W karcie __Dźwięki__ zaimportuj __Fairydust__ z katalogu __Electronic__. 

2. __Dodaj poniższy skrypt do wiedźmy__:

```scratch

	kiedy kliknięto duszek1

	ukryj

	zagraj dźwięk Fairydust
```
###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wiedźma znika i gra muzykę, kiedy się na nią kliknie?

Zapisz swój projekt

###Rzeczy do spróbowania
__Zapytaj osoby prowadzącej zajęcia, czy można nagrywać własne dźwięki do odegrania.__

##KROK 4: Dodaj punkty i licznik czasu

Mamy wiedźmę, ale teraz chcemy zrobić grę! Chcemy liczyć punkty za każde kliknięcie wiedźmy oraz chcemy dodać limit czasu do gry. Możemy użyć zmiennych na wynik i licznik czasu.

1. Stwórz nową zmienną dla wszystkich duszków i nazwij ją __Wynik__ i zmodyfikuj skrypt wiedźmy, aby wartość tej zmiennej zwiększała się o jeden przy każdym kliknięciu.

```scratch

	kiedy kliknięto duszek1

	ukryj

	zagraj dźwięk Fairydust

	zmień Wynik o 1
```

2. Switch to the __Stage__ and create a __new variable__ (this time just for the stage) called __timer__. Add a new script that occurs when the green flag is clicked to set `timer` to __30__ and reset the score to __0__. Then use a `repeat until` block to wait a second and then reduce `timer` by
one. This should repeat until timer is 0, at which point use `stop all` to stop the game.

```scratch

	when FLAG clicked

	set timer to 30

	set score to 0

	repeat until timer = 0

		wait 1 secs

		change timer by -1

	(end repeat)

	stop all
```


###Test Your Project
__Click the green flag.__ 

Save your project

###Things to try
__How might you make the witch speed up as the game goes on?__


__Well done you’ve finished the basic game. There are more things you can do to your game though. Have a go at this challenge!__

##Challenge: add more witches

If one witch is good, more must be better! __Let’s have three witches flying around.__
1. Duplicate the witch by __right-clicking__ it in the sprite list.
2. For each witch __adjust the size of the sprite__ so the witches are different sizes.
3. For each witch change the __speed variable__ so that they fly at different speeds.
4. Move the witches around the canvas so that they are not all together.

###Test Your Project
__Click the green flag.__ 

Do you have three witches that move from side to side across the screen, randomly appear and disappear, and disappear when you click on them?

Save your project

###Things to try
1. __How many witches is a good number for the game?__
2. __Can you make the witches look different? You could either edit their costumes, or use some blocks from the Looks palette to change them.__
3. __Can you make the witches be worth different points? How about making the fastest (and smallest) witch worth 10 points?__


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
