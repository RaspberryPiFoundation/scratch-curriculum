Poziom 2

#Pustynny wyścig

__Wstęp:__
Jest to gra dla dwóch graczy, podczas której papuga i lis ścigają się po pustyni. Gracze kierują swoją postacią wciskając szybko klawisz na klawiaturze. Zwierze, które pierwsze dotrze do krawędzi ekranu wygrywa.


##KROK 1: Stwórz scenę i dodaj duszki

1. Kliknij na scenę i dodaj tło z pustynią.
2. Dodaj nowego duszka i wybierz kostium lwa z katalogu ze zwierzętami.
3. Dodaj kolejnego duszka i wybierz kostium papugi.


##KROK 2: Spraw, aby lew i papuga się ruszały

Chcemy, aby duszek się ruszał, kiedy naciskasz klawisz.

1. Na początek wybierzmy lwa i ustawmy, aby poruszał się o 4 kroki po wciśnięciu klawisza 'L'

```scratch

	kiedy klawisz l naciśnięty
	przesuń o 4 kroków
```

2. Teraz pora na papugę. Ustawmy, aby przesuwała się o 4 kroki po wciśnięciu klawisza 'A'.

```scratch

	kiedy klawisz a naciśnięty
	przesuń o 4 kroków
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę__ 
Czy lew i papuga poruszają się po ekranie, gdy wciskasz 'A' i 'L'?

Zapisz swój projekt.


##KROK 3: Rozpoczęcie wyścigu

Aby móc określić później, kto wygrał, musimy najpierw wiedzieć, kiedy wyścig się rozpoczął. __Dodajmy przycisk Start.__

1. Dodaj nowego duszka i wybierz kostium przycisku z katalogu "things". Nazwij go Start.
2. Przejdź do edycji kostiumu, napisz na nim 'Start' i wciśnij OK. Przesuń duszka na środek sceny.
3. Dodaj do niego skrypt, który pokazuje przycisk, kiedy gra jest uruchomiona:

```scratch

	kiedy kliknięto flagę
	pokaż
```
4. Teraz chcemy, aby przycisk odliczał od 3 i ogłosił start wyścigu, a następnie się schował. Dodaj poniższy skrypt:

```scratch

	kiedy kliknięto Start
	powiedz 3 przez 1 s
	powiedz 2 przez 1 s
	powiedz 1 przez 1 s
	powiedz Start! przez 1 s
	ukryj
```
###Przetestuj swój projekt
__Wciśnij zieloną flagę__

Czy widzisz odliczanie po kliknięciu przycisku? Czy przycisk znika po zakończeniu odliczania?

Zapisz swój projekt.

Chcemy, aby ścigający ruszali się tylko po rozpoczęciu wyścigu. Chcemy też wiedzieć, kiedy wyścig się zakończył. Będziemy potrzebować zmiennej do przechowywania tej informacji.

5. Dodaj zmienną do wszystkich duszków i nazwij ją wyścig. Odznacz pole przy niej, aby nie było jej widać na scenie.
6. Teraz ustaw wyścig na 0, kiedy gra się rozpocznie. Dodaj ten krok do skryptu przycisku:

```scratch

	kiedy kliknięto flagę
	pokaż
	ustaw wyścig na 0
```

7. Następnie ustaw, aby zmienna wyścig zmieniała się na 1 po skończeniu odliczania do rozpoczęcia wyścigu.
8. Teraz musimy się upewnić, że lew i papuga mogą się ruszać tylko wtedy, kiedy zmienna wyścig jest ustawiona na 1. Kliknij na duszka z papugą. __Dodaj blok kontroli do skryptu, który sprawdza, czy zmienna jest równa 1:

```scratch
	
	kiedy klawisz a naciśnięty
	jeżeli wyścig = 1
		przesuń o 4 kroków
	(koniec jeżeli)
```
9. Ustaw to samo dla lwa.

###Przetestuj swój projekt
__Wciśnij zieloną flagę__

Czy lew i papuga ruszają się tylko po zakończeniu odliczania?

Teraz chcemy notować, kto wygrał wyścig i usuwać tę informację po zakończeniu gry, aby można było zacząć od nowa.

##KROK 4: Kończenie wyścigu

1. Dodaj blok do skryptu papugi, który ustawia zmienną wyścig na 0, kiedy papuga dotknie brzegu ekranu.

```scratch

	kiedy klawisz a naciśnięty
	jeżeli wyścig = 1
		przesuń o 4 kroki
		jeżeli dotyka krawędź
			ustaw wyścig na 0
		(koniec jeżeli)
	(koniec jeżeli)
	
```

2. Teraz chcemy, aby papuga dała nam znać, czy wygrała. Nagraj nowy dźwięk dla papugi, który będzie odegrany, jeżeli papuga wygra! Przejdź na kartę __dźwięki__ duszka i nagraj 

3. Dodaj do skryptu komendę, która odgrywa to nagranie, gdy papuga wygra:

```scratch

	kiedy klawisz a naciśnięty
	jeżeli wyścig = 1
		przesuń o 4 kroki
		jeżeli dotyka krawędź
			ustaw wyścig na 0
			zagraj dźwięk nagrywanie1
			powiedz Papuga wygrała! przez 3 s
			(koniec jeżeli)
		(koniec jeżeli)

```
4. Powtórz to samo dla lwa.

###Przetestuj swój projekt
__Wciśnij zieloną flagę__

Czy działa rozpoczynanie wyścigu po wciśnięciu przycisku? Można się ścigać wciskając przyciski 'A' i 'L'?
Czy duszki dobrze ogłaszają, który z nich wygrał?

Zapisz swój projekt.

##KROK 5: Restartowanie gry

Po zakończeniu wyścigu musimy powiedzieć wszystkim duszkom, że to koniec i zresetować grę, aby mogła się zacząć od nowa.

__Potrzebujemy, aby duszek, który wygra, ogłosił swoje zwycięstwo.__

1. Kliknij na papugę i dodaj do skryptu ogłaszanie końca wyścigu po wygranej.

```scratch

	kiedy klawisz a naciśnięty
	jeżeli wyścig = 1
		przesuń o 4 kroki
		jeżeli dotyka krawędź
			ustaw wyścig na 0
			zagraj dźwięk nagrywanie1
			powiedz Papuga wygrała! przez 3 s
			nadaj koniec
		(koniec jeżeli)
	(koniec jeżeli)

```

2. Teraz musimy dodać nowy skrypt, który nasłuchuje, czy wyścig został zakończony i jeżeli tak, to przesuwa papugę na linię startu. 

```scratch

	kiedy otrzymam koniec
	ustaw x na -175
```

3. Dodaj takie same skrypty dla lwa. W przypadku tego drugiego przetestuj inne wartości dla x, aby lew i papuga byli równo ustawieni na starcie.
4. Chcemy też, aby lew i papuga byli równo ustawieni po rozpoczęciu wyścigu, więc dodaj do obu duszków poniższy skrypt, który ustawia je równo po wciśnięciu flagi:

```scratch

	kiedy kliknięto flagę
	ustaw x na -175
```
5. Przejdź do duszka przycisku i dodaj skrypt, który go pokazuje po otrzymaniu komunikatu, że wyścig się zakończył.

###Przetestuj swój projekt
__Wciśnij zieloną flagę__

Możesz się ścigać z przyjacielem, kiedy jedno z was kieruje papugą wciskając 'A', a drugie kieruje lwem wciskając 'L'?

Zapisz swój projekt.

##Wyzwanie: Dodaj dopalacz

* __Spróbuj dodać dopalacz__, który każdy duszek może użyć tylko raz podczas wyścigu. Dopalacz przesuwa postać w przód o __30 kroków__.
* __Dodaj nowy kostium__ z płomieniem za każdym duszkiem i ustaw, aby się pokazywał, kiedy dopalacz zostanie użyty.
* __Nagraj następny dźwięk__, który wydadzą duszki po użyciu dopalacza.

###Przetestuj swój projekt

Zapisz swój projekt.


__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
