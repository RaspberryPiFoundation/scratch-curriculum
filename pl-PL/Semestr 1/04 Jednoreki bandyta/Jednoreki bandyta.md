---
title: Jednoręki bandyta
level: Poziom 2
language: pl-PL
stylesheet: scratch
embeds: "*.png"
materials: "*.sb"
note: "Informacje dla prowadzacych zajecia.md"
...

# Wstęp {.intro}

Prosta gra z trzema duszkami, które się zmieniają w trakcie gry. Jeżeli po zatrzymaniu wszystkie duszki wyglądają tak samo – gratulacje! Tak jak w jednorękim bandycie, takie same duszki wygrywają.

# Krok 1: Tworzenie duszka, który zmienia kostiumy {.activity}

__Zaimportujmy potrzebne obrazki do gry__

1. Rozpocznij nowy projekt w Scratchu. Usuń kota, klikając na nim prawym przyciskiem myszki i wybierając 'usuń'.
2. Zaimportuj nowego duszka.
3. Wybierz obrazek z dowolnego katalogu. My użyliśmy 'bananas1' z katalogu 'Things', ale możesz wybrać dowolny obrazek, który ci się podoba.
4. Kliknij na zakładkę 'Kostiumy' i wybierz dwa inne obrazki – potrzebujemy w sumie trzy różne kostiumy (my wybraliśmy 'bee1' z katalogu 'Animals' i 'lego' z katalogu 'Things', ale możesz wybrać którekolwiek chcesz).

__Skoro mamy już kostiumy, teraz sprawmy, aby duszek nosił je wszystkie na zmianę.__

# Krok 2: Zmieniamy pojawiające się obrazki {.activity}

1. Przejdź do zakładki Skrypty.
2. Kliknij na palecie Kontrola i przeciągnij blok "kiedy kliknięto FLAGĘ" na obszar ze skryptami.
3. Dodaj blok "zawsze" i dołącz go do bloku z flagą.
4. Kliknij na palecie Wygląd i dołacz do skryptu blok "następny kostium". Kliknij zieloną flagę.
6. Co możemy zrobić, aby obrazki nie zmieniały się tak szybko? Dodaj blok "czekaj 1 s" z palety Kontrola.
7. Zmień czas, aby obrazki zmieniały się troszkę szybciej, ale nie za szybko - 0.1 s powinno być w sam raz. Co się stanie, jeżeli usuniemy ze skryptu blok "czekaj"?

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		następny kostium
		czekaj 0.1 s
	(koniec zawsze)
```

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy kostiumy zmieniają się z rozsądną szybkością?

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
Zmień ilość sekund w bloku "czekaj". Jak myślisz, przy jakiej wartości gra stanie się zbyt prosta, a przy jakiej wartości będzie za trudna?

# Krok 3: Zatrzymujemy obrazki kliknięciem klawisza myszki {.activity}

Świetnie! Potrafimy już sprawić, aby kostiumy duszka zmieniały się w nieskończoność, ale jak zrobić, aby zatrzymały się, kiedy na niego klikniemy?

1. Kliknij na palecie Zmienne i stwórz nową zmienną. Nazwij ją "zatrzymano" i zaznacz, że ma być dostępna 'dla każdego duszka'. Następnie odznacz haczyk obok niej, aby nie była widoczna na Scenie.
2. Ustaw wartość "zatrzymano" na 1, gdy ktoś kliknie na obrazek. Użyj do tego bloku "Kiedy kliknięto Duszek1".
3. Teraz musimy sprawić, aby obrazek przestał się zmieniać, kiedyś zmienna "zatrzymano" będzie miała wartość 1. Kliknij na palecie Kontrola i zamień pętlę "zawsze" na pętlę "zawsze, jeżeli" w bloku "kiedy kliknięto FLAGĘ". Użyj wyrażenia ze znakiem równości, aby sprawdzić, czy "zatrzymano" jest równe 0.
4. Na koniec dodaj "ustaw zatrzymano na 0" zaraz pod kliknięciem we flagę.

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę, poczekaj chwilę i kliknij na duszka.__

Czy duszek zmienia kostium, zanim na niego klikniesz?

Czy duszek zatrzymuje się po kliknięciu?

__Uruchom skrypt jeszcze raz.__

Czy duszek zatrzymuje się, jeżeli najedziesz na niego kursorem myszki, ale nie klikniesz? Czy zatrzymuje się, jeżeli klikniesz gdzie indziej na Scenie? Gdzie indziej w oknie Scratcha? A gdy klikniesz gdzieś poza oknem Scratcha?

## Zapisz swój projekt. {.save}

#Step 4: Dodajemy dodatkowe duszki
__Teraz potrzebujemy stworzyć dwa inne duszki, abyśmy mogli zagrać w naszą grę!__

1. Zduplikuj duszka (Duszek1), klikając na nim prawym przyciskiem myszki.
2. Zduplikuj go jeszcze raz, tak aby były w sumie trzy.
3. Poprzesuwaj duszki na Scenie, tak aby były obok siebie. Jeśli chcesz, możesz je trochę zmniejszyć.

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Wszystkie duszki powinny się zmieniać. Spróbuj zatrzymać je na tym samym obrazku!

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
Gdy zaczynasz grę, wszystkie duszki pokazują ten sam kostium i zmieniają się razem w taki sam sposób. Może spróbuj to zmienić tak, aby kostiumy zmieniały się losowo po wciśnięciu flagi?

Wskazówka: spróbuj wylosować strój dla każdego duszka po rozpoczęciu gry.

__Brawo! Udało ci się skończyć podstawową wersję gry! Jest jeszcze kilka rzeczy, które możesz zmienić w grze. Zmierz się z poniższymi wyzwaniami!__

#Wyzwanie 1: Zwiększ poziom trudności gry

Zwiększmy poziom trudności gry. Zwiększenie prędkości, z jaką zmieniają się obrazki, jest najprostym rozwiązaniem. Spróbuj czegoś bardziej wyszukanego. Oto kilka pomysłów, które mogą ci się spodobać:

1. Zmień ilość kostiumów dla każdego duszka.
2. Dodaj unikalne kostiumy niektórym duszkom.
3. Spraw, aby kostiumy zmieniały się z różną prędkością dla różnych duszków.
4. Spraw, aby każdy duszek losował nowy kostium zamiast po prostu przechodzić do następnego.

__Baw się dobrze, wymyślając swoje własne modyfikacje!__

Za każdym razem, jak coś zmieniasz, zastanów się, jaki ma to wpływ na poziom trudności gry. Czy gra robi się łatwiejsza czy trudniejsza? Jak możesz zmienić poziom trudności tak, aby był w sam raz?

#Wyzwanie 2: Dodaj zmienny poziom trudności: niech gra staje się coraz łatwiejsza lub coraz trudniejsza w miarę upływu czasu

Różni ludzie różnie sobie radzą z grą. __Jak możesz zmodyfikować grę, aby dopasowywała swój poziom trudności do zdolności gracza?__

Jednym z rozwiązań jest __dopasowanie prędkości, z jaką zmieniają się kostiumy__. Możesz dodać zmienną o nazwie __opóźnienie__, aby kierować blokiem "czekaj". Jeżeli gracz wygra rundę, opóźnienie może się zmniejszyć (co podniesie nieco poziom trudności gry). Jeżeli gracz przegra rundę, opóźnienie może wzrosnąć, co ułatwi nieco grę.

#Wyzwanie 3: Sprawdź, kiedy wszystkie duszki zatrzymały się na tym samym obrazku

__Celem gry jest takie kliknięcie na duszki, aby zatrzymały się wszystkie pokazując ten sam kostium. Byłoby fajnie, gdyby Scena potrafiła wykryć, kiedy runda się skończyła i jaki był wynik gry. Scena mogłaby sprawdzać, czy wszystkie duszki są takie same.__

Po pierwsze, Scena musi wiedzieć, kiedy gracz skończył. Aby to zrobić, musi sprawdzać, czy wszystkie duszki przestały się ruszać po kliknięciu na jednym z nich. Zmodyfikuj blok "kiedy kliknięto Duszek" dla każdego duszka i nadawaj komunikat "sprawdźCzyKoniec".

Scena może odpowiedzieć na ten komunikat i sprawdzić, czy gra się skończyła, sprawdzając czy zmienna "zatrzymano" jest ustawiona na 1 dla wszystkich duszków. Możemy do tego użyć bloku "współrzędna x z Duszek" dla każdego duszka i zamienić "współrzędną x" na zmienną "zatrzymano". Jeżeli wartość zmiennej "zatrzymano" jest równa 1 dla wszystkich duszków, wówczas wiemy, że gra się skończyła i możemy sprawdzić czy gracz wygrał.

Użyjmy w tym celu tego samego bloku "współrzędna x z Duszek", ale zamiast sprawdzać wartość zmiennej "zatrzymano", możemy sprawdzić numer kostiumu i upewnić się, że kostium Duszka1 jest taki sam jak Duszka2, i że kostium Duszka2 jest taki sam jak Duszka3.

Żeby to zrobić, użyjemy bloku "jeżeli", który będzie sprawdzał każdą zmienną "zatrzymano", a wewnątrz niego bloku "jeżeli... w przeciwnym przypadku", który będzie porównywał numery kostiumów, aby upewnić się, czy gracz wygrał.

Możesz teraz ogłosić wynik gry, korzystając z nadawania komunikatów, które mogą zostać odebrane przez innego duszka. Na przykład, Feliks mógłby pojawić się i pogratulować graczowi.

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__

Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
