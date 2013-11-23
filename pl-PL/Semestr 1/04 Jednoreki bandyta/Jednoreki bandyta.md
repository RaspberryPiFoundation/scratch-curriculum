Poziom 2

#Jednoręki bandyta

__Wstęp:__
Prosta gra z trzema duszkami, które zmieniają swój kostium. Trzeba je zatrzymać, kiedy wszystkie wyglądają tak samo (podobnie jak w jednorękim bandycie!).

##KROK 1: Tworzenie duszka, który zmienia kostiumy

__Zaimportujmy potrzebne obrazki do gry__

1. Zacznij nowy projekt w Scratchu. Skasuj kota, klikając na nim prawym przyciskiem myszy i wybierając Usuń.
2. Zaimportuj nowego duszka.
3. Wybierz obrazek z dowolnego katalogu. My użyliśmy "bananas1" z katalogu Things, ale możesz wybrać dowolny obrazek, który ci się podoba.
4. Kliknij na kartę Kostiumy i wybierz dwie inne rzeczy, bo w sumie potrzebujemy trzy kostiumy (my wybraliśmy "bee1" z katalogu Animals i "lego" z katalogu Things, ale możesz wybrać co chcesz). 

__Skoro mamy już kostiumy, teraz chcemy, aby duszek nosił je wszystkie na zmianę.__

##KROK 2: Sprawianie, aby obrazki się zmieniały

1. Przejdź do karty Skrypty.
2. Wybierz Kontrola i przeciągnij "kiedy kliknięto FLAGĘ" na obszar ze skryptami. Ten blok zostanie uruchomiony po wciśnięciu zielonej flagi w rogu nad Sceną.
3. Dodaj blok "zawsze" i upewnij się, że jest przyczepiony do dołu bloku z flagą.
4. Wciśnij zieloną flagę. Zauważ, że wokół naszego skryptu pojawia się biała ramka. Oznacza to, że skrypt się wykonuje po wciśnięciu zielonej flagi, która uruchamia wszystkie skrypty.
5. Wciśnij Wygląd w obszarze w lewym górnym rogu i przeciągnij do skryptu "następny kostium". Wciśnij flagę.
6. Co zrobić, żeby obrazki nie zmieniały się tak szybko? Dodaj blok "czekaj 1 s" z sekcji Kontrola.
7. Zmień czas, aby obrazki zmieniały się szybko, ale nie za szybko, np. 0.1 s wygląda dobrze. Co by się stało, gdybyśmy usunęli blok "czekaj"?

```scratch

	kiedy kliknięto FLAGĘ
	zawsze		
		następny kostium		
		czekaj 0.1 s		
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Czy kostiumy zmieniają się z rozsądną szybkością?

Zapisz swój projekt.

###Rzeczy do spróbowania
Zmień czas oczekiwania. Jak myślisz, jaki czas robi grę zbyt łatwą? A jaki sprawia, że jest za trudna?

##KROK 3: Zatrzymywanie zmieniających się obrazków kliknięciem myszki

Świetnie! Potrafimy już sprawić, aby kostiumy duszka zmieniały się w nieskończoność, ale jak zrobić, aby zatrzymały się, jak się na niego kliknie?

2. Kliknij na Zmienne i stwórz nową. Nazwij ją "zatrzymano" i zaznacz, że ma być dostępna dla wszystkich duszków. Następnie odznacz haczyk koło niej, aby nie była widoczna na Scenie.
2. Ustaw wartość "zatrzymano" na 1, gdy ktoś kliknie na obrazek. Użyj do tego bloku "Kiedy kliknięto duszek1".
3. Teraz musimy sprawić, aby obrazek przestał się zmieniać, kiedyś zmienna "zatrzymano" będzie miała wartość 1. Kliknij na Kontrolę i zamień pętlę "zawsze" na pętlę "zawsze, jeżeli" w bloku "kiedy kliknięto FLAGĘ". Użyj wyrażenia ze znakiem równości, aby sprawdzić, czy "zatrzymano" jest równe 0.
4. Na koniec dodaj "ustaw zatrzymano na 0" zaraz pod kliknięciem we flagę.

###Przetestuj swój projekt
__Kliknij zieloną flagę, poczekaj chwilę i kliknij na duszka.__

Czy duszek zmienia kostium, zanim na niego klikniesz?
Czy duszek zatrzymuje się po kliknięciu?
__Uruchom skrypt jeszcze raz.__ Czy duszek zatrzymuje się, jeżeli po prostu ustawisz na nim kursor, ale nie klikniesz? Czy zatrzymuje się, jeżeli klikniesz gdzie indziej na Scenie? Gdzie indziej w oknie Scratcha? A gdy klikniesz gdzieś poza oknem Scratcha?

Zapisz swój projekt.

##Step 4: Tworzenie innych duszków
__Teraz potrzebujemy stworzyć dwa inne duszki, aby można było grać w naszą grę!__

1. Zduplikuj duszka (Duszek1), klikając na nim prawym przyciskiem myszki.
2. Zduplikuj go jeszcze raz, tak aby były w sumie trzy duszki na obszarze w prawym dolnym rogu ekranu.
3. Poprzesuwaj duszki na Scenie, tak aby były obok siebie. Możesz je trochę zmniejszyć, jeśli chcesz.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__ Wszystkie duszki powinny się zmieniać. Spróbuj zatrzymać je na tym samym obrazku!

Zapisz swój projekt.

###Rzeczy do spróbowania
Gdy zaczynasz grę, wszystkie duszki pokazują ten sam kostium i zmieniają się razem. Co ty na to, aby sprawić, żeby zaczęły zmieniać kostiumy losowo po wciśnięciu flagi?
Wskazówka: spróbuj wybierać losowy strój dla każdego duszka po rozpoczęciu gry.

__Brawo! Udało ci się skończyć podstawową wersję gry! Jest jeszcze kilka rzeczy, które możesz zmienić w grze. Zmierz się z poniższymi wyzwaniami!__

##Wyzwanie 1: Zwiększ poziom trudności gry

Zwiększ jakoś poziom trudności gry. Zwiększenie prędkości, z jaką zmieniają się obrazki, jest prostym rozwiązaniem. Spróbuj czegoś bardziej wyszukanego. Kilka pomysłów, które mogą ci się spodobać:

1. Zmień ilość kostiumów dla każdego duszka.
2. Dodaj unikalne kostiumy niektórym duszkom.
3. Ustaw, aby kostiumy zmieniały się z różną prędkością.
4. Ustaw, aby każdy duszek losował nowy kostium zamiast po prostu przechodzić do następnego.

__Baw się dobrze, wymyślając swoje własne modyfikacje!__

Za każdym razem, jak coś zmieniasz, zastanów się, jaki ma to wpływ na poziom trudności gry. Robi się łatwiejsza czy za trudna? Jak możesz zmienić poziom trudności tak, aby był w sam raz?

##Wyzwanie 2: Dodaj zmienny poziom trudności: coraz trudniej/coraz łatwiej wraz z czasem gry

Różni ludzie różnie sobie radzą podczas grania w grę. __Jak możesz zmodyfikować grę, aby dopasowywała swój poziom trudności w zależności od gracza?__

Jednym rozwiązaniem jest __dopasowanie prędkości, z jaką zmieniają się kostiumy__. Możesz dodać zmienną o nazwie __opóźnienie__, aby kierować blokiem "czekaj". Jeżeli gracz wygra rundę, opóźnienie może się zmniejszyć (co podniesie nieco poziom trudności gry). Jeżeli gracz przegra rundę, opóźnienie może wzrosnąć, co ułatwi nieco grę.

##Wyzwanie 3: Wykrywaj, kiedy wszystkie duszki zatrzymały się na tym samym kostiumie

__Celem gry jest takie kliknięcie na duszki, aby zatrzymały się wszystkie pokazując ten sam kostium. Byłoby fajnie, gdyby Scena potrafiła wykryć, kiedy runda się skończyła i jaki był wynik gry. Scena mogłaby sprawdzać, czy wszystkie duszki były takie same.__

Po pierwsze, Scena musi wiedzieć, kiedy gracz skończył. Aby to zrobić, możemy ustawić, aby Scena sprawdzała, czy wszystkie duszki przestały się ruszać po kliknięciu na jednego z nich. Zmodyfikuj blok "kiedy kliknięto Duszek" dla każdego duszka i dodaj nadawanie komunikatu "sprawdźCzyKoniec".

Scena może odpowiedzieć na ten komunikat i sprawdzić, czy gra się skończyła, sprawdzając czy zmienna "zatrzymano" jest ustawiona na 1 dla wszystkich duszków. Możemy do tego użyć bloku "współrzędna x z Duszek" dla każdego duszka i zamienić "współrzędną x" na zmienną "zatrzymano". Jeżeli wartość zmiennej "zatrzymano" jest równa 1 dla wszystkich duszków, wiemy, że gra się skończyła i gracz wygrał.

Możemy też do tego użyć tego samego bloku "współrzędna x z Duszek", ale zamiast sprawdzać wartość zmiennej "zatrzymano", możemy sprawdzić numer kostiumu i upewnić się, że kostium Duszka1 jest taki sam jak Duszka2, i że kostium Duszka2 jest taki sam jak Duszka3.

Żeby to zrobić, potrzebujemy blok "jeżeli", który będzie sprawdzał każdą zmienną "zatrzymano", a wewnątrz niego blok "jeżeli… w przeciwnym przypadku", który będzie porównywał numery kostiumów, aby upewnić się, czy gracz wygrał.

Możesz teraz ogłosić wynik gry, korzystając z nadawania komunikatów, które mogą zostać odebrane przez innego duszka. Na przykład, Feliks mógłby pojawić się i pogratulować graczowi.

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
