Poziom 1

#Przegoń wiedźmy

__Wstęp:__
Ten projekt jest jak popularna gra zwana Whack-A-Mole: zdobywasz punkty klikając wiedźmy, które pojawiają się na ekranie. Celem gry jest zdobycie jak największej ilości punktów w ciągu 30 sekund.

##KROK 1: Stwórz latającą wiedźmę

1. __Zacznij nowy projekt w Scratchu.__
2. __Usuń duszka kota__ i zastąp tło lasem z katalogu __Nature__.
3. Użyj przycisku "wybierz nowego duszka z pliku", aby dodać wiedźmę do projektu (znajdź kostium __witch1__ w katalogu __Fantasy__).

__Teraz chcemy sprawić, aby wiedźma zaczęła się ruszać__

4. Dodaj Zmienną tylko dla tego duszka i nazwij ją "prędkość".
Nowa zmienna powinna pojawić się na __Scenie__ jako "__Duszek1 prędkość".
Jeżeli widzisz tam tylko "prędkość", skasuj zmienną i stwórz nową jeszcze raz tylko dla tego jednego duszka. 
Odznacz "prędkość" w __panelu Zmiennych__, aby nie było widać jej na Scenie.
Ta zmienna będzie kontrolować jak szybko wiedźma się rusza. Korzystamy ze zmiennej, aby móc zmieniać prędkość wiedźmy wraz z postępami w tworzeniu gry.
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

6. Aby wiedźma nie utykała, musimy sprawić, że będzie zawracać za każdym razem, gdy doleci do brzegu ekranu. W jej skrypcie, poniżej bloku "przesuń o prędkość kroków" dodaj blok "jeżeli na brzegu, odbij się".


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

Zapisz swój projekt.

###Rzeczy do spróbowania
__Spróbuj zmieniać wartość zmiennej prędkości, aby sprawić, żeby wiedźma latała szybciej i wolniej.__

__Co zrobić, aby wiedźma była coraz szybsza im dłużej lata?__
(To jest trochę skomplikowane, więc nie martw się, jeżeli nie widzisz jeszcze rozwiązania. Dostaniesz więcej wskazówek podczas dalszej pracy nad projektem.)

##KROK 2: Spraw, aby wiedźma pojawiała się i znikała losowo

Aby gra była ciekawsza, chcemy, aby wiedźma pojawiała się i znikała losowo. Będzie nam do tego potrzebny kolejny skrypt, który działa w tym samym czasie co ten odpowiedzialny za poruszanie wiedźmą. Nowy skrypt powinien chować wiedźmę w losowych momentach, pokazywać ją znowu po jakimś czasie i powtarzać te dwie akcje w nieskończoność (albo do końca gry).

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
Czy wiedźma lata od brzegu do brzegu ekranu oraz pojawia się i znika w losowych momentach?

Zapisz swój projekt.

###Rzeczy do spróbowania
__Spróbuj zmieniać przedział liczb losowych. Co się dzieje, jeżeli wybierzesz bardzo duże albo bardzo małe liczby?__
Czy podpowiada ci to już jak sprawić, aby wiedźma latała coraz szybciej?)

##KROK 3: Spraw, aby wiedźma znikała, gdy się na nią kliknie

Aby zamienić ten projekt w grę, musimy dać graczom coś do robienia. Niech klikają wiedźmę, aby zniknęła. Chcemy, aby po kliknięciu było słuchać dźwięk i aby wiedźma znikała z ekranu.

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

Zapisz swój projekt.

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

2. Przełącz na __Scenę__ i stwórz nową zmienną (tym razem tylko da sceny) o nazwie __Czas__. Dodaj nowy skrypt ustawiający czas na __30__ oraz wynik na __0__, który zostaje wykonany po wciśnięciu zielonej flagi. Skorzystaj z bloku "powtarzaj aż", aby czekać sekundę i potem obniżać czas o 1. Akcja powinna powtarzać się dopóki licznik czasu nie dojdzie do zera, kiedy to "zatrzymaj wszystko" zostanie wykonane i zakończy grę.

```scratch

	kiedy kliknięto FLAGĘ
	ustaw Czas na 30
	ustaw Wynik na 0
	powtarzaj aż Czas = 0
		czekaj 1 s
		zmień Czas o -1
	(koniec powtarzaj)
	zakończ wszystko
```


###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Zapisz swój projekt.

###Rzeczy do spróbowania
__Jak można sprawić, żeby wiedźma latała coraz szybciej?__

__Udało ci się skończyć podstawową wersję gry, ale ciągle są rzeczy, które możesz zmienić w grze. Mamy dla ciebie wyzwanie!__

##Wyzwanie: dodaj więcej wiedźm

Jeżeli jedna wiedźma jest dobra, to im ich więcej, tym lepiej! __Zróbmy trzy latające wiedźmy.__

1. Zduplikuj wiedźmę klikając na nią __prawym przyciskiem myszy__ na liście duszków.
2. __Zmień rozmiar każdej wiedźmy__, aby każda z nich była inna.
3. Zmień __zmienną "prędkość"__ dla każdej wiedźmy, aby każda z nich była inna.
4. Poprzesuwaj wiedźmy po ekranie, aby nie latały wszystkie razem.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy masz trzy wiedźmy, które latają od brzegu do brzegu ekranu, pojawiają się i znikają niespodziewanie, oraz znikają po kliknięciu na nie?

Zapisz swój projekt.

###Rzeczy do spróbowania?
2. __Jak dużo wiedźm jest w sam raz dla tej gry?__
2. __Czy możesz sprawić, żeby wiedźmy wyglądały inaczej? Może by zmienić ich kostiumy albo wybrać zupełnie inny wygląd?__
3. __Czy możesz zmienić liczbę punktów, które dostaje się za różne wiedźmy? Na przykład najszybsza (i najmniejsza) mogłaby być warta 10 punktów.__


__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.