Poziom 1

#Przegoń wiedźmy

__Wstęp:__

Ten projekt jest bazuje na popularnej angielskiej grze zwanej Whack-A-Mole: zdobywasz punkty klikając wiedźmy, które pojawiają się na ekranie. Celem gry jest zdobycie jak największej ilości punktów w ciągu 30 sekund.

##KROK 1: Stwórz latającą wiedźmę

1. __Stwórz nowy projekt.__
2. __Usuń duszka kota__ i zastąp tło lasem (woods) z katalogu __Nature__.
3. Kliknij przycisk "Wybierz nowego duszka z pliku" i dodaj wiedźmę do projektu (znajdź kostium __witch1__ w katalogu __Fantasy__).

    __Teraz sprawmy, aby wiedźma zaczęła latać__

4. Dodaj zmienną 'Tylko dla tego duszka' i nazwij ją "prędkość". Nowa zmienna powinna pojawić się na __Scenie__ jako __"Duszek1 prędkość"__.

    Jeżeli widzisz tam tylko "prędkość", usuń zmienną i stwórz ją na nowo, tylko tym razem wybierz opcję 'Tylko dla tego duszka'.

    Odznacz "prędkość" w __panelu Zmiennych__, aby nie było jej widać na Scenie. Ta zmienna będzie kontrolować prędkość lotu naszej wiedźmy. Korzystamy ze zmiennej, aby móc później zmieniać prędkość lotu wiedźmy.

5. Chcemy, aby wiedźma zaczęła latać zaraz po rozpoczęciu gry. __Stwórz dla niej poniższy skrypt__:

```scratch

	kiedy kliknięto FLAGĘ
	ustaw prędkość na 5
	zawsze
		przesuń o prędkość kroków
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę__ i zobacz, co robi wiedźma. Dlaczego utknęła na brzegu ekranu?

1. Aby wiedźma nie zatrzymywała się na brzegu ekranu, musimy sprawić, aby zawracała za każdym razem, gdy doleci do brzegu ekranu. Dodajmy blok "jeżeli na brzegu, odbij się" poniżej bloku "przesuń o prędkość kroków" w skrypcie wiedźmy.

    ```scratch

        kiedy kliknięto FLAGĘ
        ustaw prędkość na 5
        zawsze
            przesuń o prędkość kroków
            jeżeli na brzegu, odbij się
        (koniec zawsze)
    ```

2. Aby wiedźma nie obracała się do góry nogami, wybierz opcję "odwróć tylko w prawo-lewo" w ustawieniach tego duszka.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wiedźma lata od brzegu do brzegu ekranu?

Zapisz swój projekt.

###Rzeczy do spróbowania
__Spróbuj zmienić wartość zmiennej prędkość, aby sprawić, żeby wiedźma latała szybciej lub wolniej.__

__Co zrobić, aby wiedźma leciała coraz szybciej w trakcie gry?__

(Jest to troszkę skomplikowane, więc nie przejmuj się, jeżeli jeszcze nie wiesz jak to zrobić. Podpowiemy Ci troszkę później jak to zrobić.)

##KROK 2: Spraw, aby wiedźma losowo pojawiała się i znikała

Aby gra była ciekawsza, spróbujemy sprawić, aby wiedźma losowo pojawiała się i znikała. Będzie nam do tego potrzebny kolejny skrypt, który działa w tym samym czasie co ten odpowiedzialny za poruszanie wiedźmą. Nowy skrypt powinien niespodziewanie ukryć wiedźmę, i po jakimiś czasie znowu pokazać ją na ekranie (i robić to cały czas w trakcie gry).

__Dodajmy wiedźmie poniższy skrypt:__

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

Czy wiedźma lata od brzegu do brzegu ekranu oraz losowo pojawia się i znika z ekranu?

Zapisz swój projekt.

###Rzeczy do spróbowania
__Spróbuj zmienić wartość liczb, które użyliśmy do ukrywania i pojawiania się wiedźmy. Co się stanie, jeżeli wybierzemy bardzo duże albo bardzo małe liczby?__

Czy pomoże Ci to sprawić, aby wiedźma latała coraz szybciej?

##KROK 3: Spraw, aby wiedźma znikała, gdy na nią klikniesz

Aby zamienić ten projekt w grę, musimy dać graczom coś do zrobienia. Niech klikają w wiedźmę, aby zniknęła. Chcemy, aby po kliknięciu w wiedźmę było słuchać jakiś dźwięk a sama wiedźma zniknęła z ekranu.

1. W zakładce __Dźwięki__ zaimportuj dźwięk __Fairydust__ z katalogu __Electronic__.

2. __Dodajmy wiedźmie poniższy skrypt__:

```scratch

	kiedy kliknięto Duszek1
	ukryj
	zagraj dźwięk Fairydust
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wiedźma znika i wydaje dźwięk, jak nią klikniesz?

Zapisz swój projekt.

###Rzeczy do spróbowania
__Zapytaj osoby prowadzącej zajęcia, czy możesz spróbować nagrywać własny dźwięk i użyć go w swoim projekcie.__

##KROK 4: Dodaj punkty i zegar

Mamy już naszą wiedźmę, więc wykorzystajmy ją do stworzenia naszej gry! Zacznijmy liczyć punkty za każde kliknięcie na wiedźmie oraz dodajmy limit czasu do gry. Do tym celu użyjemy 2 nowe zmienne.

1. Stwórz nową zmienną 'Dla każdego duszka' i nazwij ją __Wynik__. Zmieńmy skypt wiedźmy tak, aby przy każdym kliknięciu wartość tej zmiennej zwiększała się o jeden punkt.

    ```scratch

        kiedy kliknięto Duszek1
        ukryj
        zagraj dźwięk Fairydust
        zmień wynik o 1
    ```

2. Kliknij na __Scenę__, stwórz nową zmienną (tym razem tylko da sceny) i nazwij ją __czas__. Dodaj nowy skrypt ustawiający czas na __30__ oraz wynik na __0__, który zostaje wykonany po wciśnięciu zielonej flagi. Skorzystaj z bloku "powtarzaj aż", aby odczekać sekundę i zmniejszyć wartość czasu o 1. Akcja powinna powtarzać się dopóki licznik czasu nie dojdzie do zera. Wtedy to zakończymy grę używając bloku "zatrzymaj wszystko".

    ```scratch

        kiedy kliknięto FLAGĘ
        ustaw czas na 30
        ustaw wynik na 0
        powtarzaj aż czas = 0
            czekaj 1 s
            zmień czas o -1
        (koniec powtarzaj)
        zakończ wszystko
    ```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Zapisz swój projekt.

###Rzeczy do spróbowania
__Jak można sprawić, aby wiedźma latała coraz szybciej?__

__Udało ci się skończyć podstawową wersję gry, ale ciągle są rzeczy, które możesz zmienić w grze. Mamy dla ciebie wyzwanie!__

##Wyzwanie: Dodaj więcej wiedźm

Gra z jedną wiedźmą jest super, ale co jeżeli dodamy więcej wiedź do gry. Na pewno gra będzie jeszcze lepsza!

__Dodajmy kolejne latające wiedźmy do naszej gry.__

1. Zduplikuj wiedźmę klikając na nią __prawym przyciskiem myszy__ na liście duszków.
2. __Zmień rozmiar każdej wiedźmy__, aby każda z nich była innej wielkości.
3. Zmień __zmienną "prędkość"__ każdej wiedźmy, aby każda z nich była latała z inną prędkością.
4. Poprzesuwaj wiedźmy po ekranie, aby nie latały wszystkie obok siebie.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy masz na ekranie kilka wiedźm, latających od brzegu do brzegu ekranu, które niespodziewanie pojawiają się i znikają? Czy wiedźmy znikają po kliknięciu na nie?

Zapisz swój projekt.

###Rzeczy do spróbowania?

1. __Jaka ilość wiedźm będzie najlepsza dla naszej gry?__
2. __Czy możesz sprawić, aby wiedźmy wyglądały inaczej? Możesz zmienić ich kostium albo wybrać zupełnie inny wygląd?__
3. __Czy możesz zmienić liczbę punktów, które dostaje się za różne wiedźmy? Na przykład najszybsza (i najmniejsza) wiedźma mogłaby być warta 10 punktów.__

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__

Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
