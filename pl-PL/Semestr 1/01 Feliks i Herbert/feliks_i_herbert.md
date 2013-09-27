Poziom 1

#Feliks i Herbert

__Wstęp:__
Zrobimy grę w berka, w której kot __Feliks__ goni mysz __Herberta__. Będziesz sterować Herbertem przy pomocy myszki i masz za zadanie unikać Feliksa. Im dłużej będziesz przed nim uciekać, tym więcej punktów dostaniesz. Nie daj się złapać, bo stracisz punkty!

##KROK 1: Feliks podąża za kursorem myszy

1. Zacznij nowy projekt.
2. Kliknij na scenie na lewo od duszka, kliknij Tła i zaimportuj tło "hall" z kategorii Indoors. Skasuj puste tło z listy.
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
Czy Feliks podąża za kursorem myszy? Czy wygląda jakby chodził? Czy porusza się z dobrą prędkością?

Zapisz swój projekt

##KROK 2: Feliks goni Herberta

__Teraz sprawimy, aby Feliks zaczął gonić Herberta zamiast podążać za kursorem.__

1. Stwórz następnego duszka. Kliknij "wybierz nowego duszka z pliku", przejdź do kategorii Animals i wybierz Mouse1.
2. Zmień nazwę duszka na Herbert.
3. Kliknij edycję kostiumu, a później zmień rozmiar Herberta, aby był mniejszy od Feliksa.
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

__Zamiast wiadomości od Feliksa, że złapał mysz, chcemy, aby Herbert zamieniał się w ducha jak zostanie złapany.__

1. Zamień skrypt Feliksa na poniższy, aby nadać wiadomość, że Herbert zostanie złapany.

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

2. Dodaj nowy kostium dla Herberta: kliknij Importuj i wybierz ghost2-a z kategorii Fantasy.
3. Zmniejsz nowy kostium.
Sześć klików na przycisku do zmniejszania powinno załatwić sprawę.

4. Zmień nazwy kostiumów Herberta: nazwij mysz "żywy" i ducha "nieżywy".
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
Czy po złapaniu Feliks nie rusza się odpowiednio długo, aby Herbert mógł uciec od niego?

Zapisz swój projekt

##KROK 5: Zbieranie punktów

__Dodajmy licznik punktów, aby było widać jak dobrze nam idzie ratowanie Herberta.
Zaczniemy od zera i będziemy dodawać jeden punkt co sekundę. Gdy Feliks złapie Herberta, odejmiemy 100 punktów.__

1. Stwórz zmienną o nazwie "Wynik" dla wszystkich duszków. Aby to zrobić, wybierz Zmienne, dodaj nową zmienną i zmień jej nazwę.
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

Czy wynik rośnie o jeden punkt co sekundę?
Czy ilość punktów spada o 100, kiedy Herbert zostanie złapany?
Co się dzieje, kiedy Herbert zostanie złapany zanim wynik wzrośnie do 100? Czy wynik zeruje się przy rozpoczęciu nowej gry?

Zapisz swój projekt

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomniej, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
