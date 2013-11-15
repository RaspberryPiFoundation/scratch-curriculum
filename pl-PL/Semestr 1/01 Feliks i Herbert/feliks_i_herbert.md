Poziom 1

#Feliks i Herbert

__Wstęp:__
Zrobimy grę w berka, w której kot Feliks goni mysz Herberta. Będziesz sterować Herbertem przy pomocy myszki i masz za zadanie nie dać się złapać Feliksowi. Im dłużej będziesz przed nim uciekać, tym więcej punktów zdobędziesz. Nie daj się złapać, bo stracisz punkty!

##KROK 1: Feliks podąża za kursorem myszy

1. Stwórz nowy projekt.
2. Kliknij na scenę na lewo od duszka, a następnie kliknij zakładkę Tła i zaimportuj tło "hall" z katalogu "Indoors". Usuń puste tło z listy.
3. Zmień nazwę duszka na Feliks.
4. Upewnij się, że Feliks obraca się tylko w lewo i prawo wciskając ten przycisk:
5. Stwórz poniższy skrypt:

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

Czy Feliks podąża za kursorem myszy? Czy wygląda jakby chodził? Czy porusza się z odpowiednią prędkością?

Zapisz swój projekt.

##KROK 2: Feliks goni Herberta

__Teraz sprawimy, aby Feliks zaczął gonić Herberta zamiast podążać za kursorem myszy.__

1. Stwórz następnego duszka. Kliknij "wybierz nowego duszka z pliku", i wybierz "Mouse1" z katalogu "Animals".
2. Zmień nazwę duszka na Herbert.
3. Kliknij przycisk edycji kostiumu i zmniejsz Herberta.
Kliknij sześć razy na przycisku do zmniejszania:
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

##KROK 3: Feliks ogłasza, że złapał Herberta

__Chcemy, aby Feliks nam powiedział że złapał Herberta.__

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

##KROK 4: Herbert zamienia się w ducha po złapaniu

__Zamiast wiadomości od Feliksa, że złapał mysz, chcemy, aby Herbert zamienił się w ducha.__

1. Zamień skrypt Feliksa na poniższy, aby nadać wiadomość o złapaniu Herberta.

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		idź do wskaźnik myszy
		przesuń o 10 kroków
		następny kostium
		zagraj bębenkiem 62 przez 0.3 taktów
		jeżeli dotyka Herbert
			nadaj złapany
			zagraj bębenkiem 58 przez 0.2 taktów
			czekaj 1 s
		(koniec jeżeli)
	(koniec zawsze)
```

2. Dodaj Herbertowi nowy kostium: kliknij Importuj i wybierz "ghost2-a" z katalogu "Fantasy".

3. Zmniejsz nowy kostium.

Sześć kliknięć na przycisku do zmniejszania powinno załatwić sprawę.

4. Zmień nazwy kostiumów Herberta: nazwij mysz "żywy", a ducha "nieżywy".

5. Dodaj nowy skrypt, który zamienia Herberta w ducha:

```scratch

	kiedy otrzymam złapany
	zmień kostium na nieżywy
	czekaj 0.5 s
	zmień kostium na żywy
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę.__

Czy Herbert zamienia się w ducha jak zostanie złapany?
Czy Feliks wydaje odpowiednie odgłosy w odpowiednich momentach?
Czy po złapaniu Feliks nie rusza się odpowiednio długo, aby Herbert mógł od niego uciec?

Zapisz swój projekt.

##KROK 5: Liczymy punkty

__Dodajmy licznik punktów, aby było widać jak dobrze nam idzie ratowanie Herberta.
Zaczniemy od zera i co sekundę będziemy dodawać jeden punkt. Gdy Feliks złapie Herberta, odejmiemy 100 punktów.__

1. Stwórz zmienną o nazwie "Wynik" "dla każdego duszka". Aby to zrobić, wybierz Zmienne, dodaj nową zmienną i zmień jej nazwę.

2. Kliknij na Scenę i dodaj oba poniższe skrypty

```scratch

	kiedy kliknięto FLAGĘ
	ustaw Wynik na 0
	zawsze
		zmień Wynik o 1
		czekaj 1 s
	(koniec zawsze)
	kiedy otrzymam złapany
	zmień Wynik o -100
```

###Przetestuj swój projekt
__Wciśnij zieloną flagę.__

Czy wynik rośnie co sekundę o jeden punkt?
Czy ilość punktów spada o 100, kiedy Herbert zostanie złapany?
Co się dzieje, kiedy Herbert zostanie złapany zanim wynik wzrośnie do 100? Czy wynik zeruje się przy rozpoczęciu nowej gry?

Zapisz swój projekt

__Brawo! To by było na tyle, teraz możesz cieszyć się swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
