---
title: Pogromcy duchów
level: Poziom 1
language: pl-PL
stylesheet: scratch
embeds: "*.png"
materials: "Pogromcy duchow.sb"
note: "informacje dla prowadzacych zajecia.md"
...

# Wstęp {.intro }

Ten projekt jest bazuje na popularnej angielskiej grze zwanej Whack-A-Mole: zdobywasz punkty klikając duchy, które pojawiają się na ekranie. Celem gry jest zdobycie jak największej ilości punktów w ciągu 30 sekund.

# Krok 1: Stwórz latającego ducha {.activity}

1. __Stwórz nowy projekt.__
2. __Usuń duszka kota__ i zastąp tło lasem (woods) z katalogu __Nature__.
3. Kliknij przycisk "Wybierz nowego duszka z pliku" i dodaj ducha do projektu (znajdź kostium __ghost2-b__ w katalogu __Fantasy__).

    __Teraz sprawmy, aby duch zaczął latać__

4. Dodaj zmienną 'Tylko dla tego duszka' i nazwij ją "prędkość". Nowa zmienna powinna pojawić się na __Scenie__ jako __"Duszek1 prędkość"__.

    Jeżeli widzisz tam tylko "prędkość", usuń zmienną i stwórz ją na nowo, tylko tym razem wybierz opcję 'Tylko dla tego duszka'.

    Odznacz "prędkość" w __panelu Zmiennych__, aby nie było jej widać na Scenie. Ta zmienna będzie kontrolować prędkość lotu naszego ducha. Korzystamy ze zmiennej, aby móc później zmieniać prędkość lotu ducha.

5. Chcemy, aby duch zaczął latać zaraz po rozpoczęciu gry. __Stwórz dla niego poniższy skrypt__:

```scratch

	kiedy kliknięto FLAGĘ
	ustaw prędkość na 5
	zawsze
		przesuń o prędkość kroków
	(koniec zawsze)
```

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę__ i zobacz, co robi duch. Dlaczego utknął na brzegu ekranu?

1. Aby duch nie zatrzymywał się na brzegu ekranu, musimy sprawić, aby zawracał za każdym razem, gdy doleci do brzegu ekranu. Dodajmy blok "jeżeli na brzegu, odbij się" poniżej bloku "przesuń o prędkość kroków" w skrypcie ducha.

    ```scratch

        kiedy kliknięto FLAGĘ
        ustaw prędkość na 5
        zawsze
            przesuń o prędkość kroków
            jeżeli na brzegu, odbij się
        (koniec zawsze)
    ```

2. Aby duch nie obracał się do góry nogami, wybierz opcję "odwróć tylko w prawo-lewo" w ustawieniach tego duszka.

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy duch lata od brzegu do brzegu ekranu?

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
__Spróbuj zmienić wartość zmiennej prędkość, aby sprawić, żeby duch latał szybciej lub wolniej.__

__Co zrobić, aby duch leciał coraz szybciej w trakcie gry?__

(Jest to troszkę skomplikowane, więc nie przejmuj się, jeżeli jeszcze nie wiesz jak to zrobić. Podpowiemy Ci troszkę później jak to zrobić.)

# Krok 2: Spraw, aby duch losowo pojawiał się i znikał {.activity}

Aby gra była ciekawsza, spróbujemy sprawić, aby duch losowo pojawiał się i znikał. Będzie nam do tego potrzebny kolejny skrypt, który działa w tym samym czasie co ten odpowiedzialny za poruszanie duchem. Nowy skrypt powinien niespodziewanie ukryć ducha i po jakimiś czasie znowu pokazać go na ekranie (i robić to cały czas w trakcie gry).

__Dodajmy duchowi poniższy skrypt:__

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		ukryj
		czekaj losuj liczbę pomiędzy 2 a 5 s
		pokaż
		czekaj losuj liczbę pomiędzy 3 a 5 s
	(koniec zawsze)
```
##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy duch lata od brzegu do brzegu ekranu oraz losowo pojawia się i znika?

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
__Spróbuj zmienić wartość liczb, które użyliśmy do ukrywania i pojawiania się ducha. Co się stanie, jeżeli wybierzemy bardzo duże albo bardzo małe liczby?__

Czy pomoże Ci to sprawić, aby duch latał coraz szybciej?

# Krok 3: Spraw, aby duch znikał, gdy na niego klikniesz {.activity}

Aby zamienić ten projekt w grę, musimy dać graczom coś do zrobienia. Niech klikają w ducha, aby zniknął. Chcemy, aby po kliknięciu w ducha było słychać jakiś dźwięk, a sam duch znikał z ekranu.

1. W zakładce __Dźwięki__ zaimportuj dźwięk __Fairydust__ z katalogu __Electronic__.

2. __Dodajmy duchowi poniższy skrypt__:

```scratch

	kiedy kliknięto Duszek1
	ukryj
	zagraj dźwięk Fairydust
```

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy ducha znika i wydaje dźwięk, gdy go klikniesz?

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
__Zapytaj osoby prowadzącej zajęcia, czy możesz spróbować nagrywać własny dźwięk i użyć go w swoim projekcie.__

# Krok 4: Dodaj punkty i zegar {.activity}

Mamy już ducha, więc wykorzystajmy go do stworzenia własnej gry! Zacznijmy liczyć punkty za każde kliknięcie na duchu oraz dodajmy limit czasu do gry. W tym celu użyjemy 2 nowe zmienne.

1. Stwórz nową zmienną 'Dla każdego duszka' i nazwij ją __Wynik__. Zmieńmy skypt ducha tak, aby przy każdym kliknięciu wartość tej zmiennej zwiększała się o jeden punkt.

    ```scratch

        kiedy kliknięto Duszek1
        ukryj
        zagraj dźwięk Fairydust
        zmień wynik o 1
    ```

2. Kliknij na __Scenę__, stwórz nową zmienną (tym razem tylko da sceny) i nazwij ją __czas__. Dodaj nowy skrypt uruchamiany kliknioęciem flagi, który ustawia czas na __30__ oraz wynik na __0__. Skorzystaj z bloku "powtarzaj aż", aby odczekać sekundę i zmniejszyć wartość czasu o 1. Akcja powinna powtarzać się dopóki licznik czasu nie dojdzie do zera. Wtedy to zakończymy grę używając bloku "zatrzymaj wszystko".

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

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania
__Jak można sprawić, aby duch latał coraz szybciej?__

__Udało ci się skończyć podstawową wersję gry, ale ciągle są rzeczy, które możesz zmienić w grze. Mamy dla Ciebie wyzwanie!__

#Wyzwanie: Dodaj więcej duchów

Gra z jednym duchem jest super, ale co jeżeli dodamy ich więcej. Na pewno gra będzie jeszcze lepsza!

__Dodajmy kolejne latające duchy do naszej gry.__

1. Zduplikuj ducha klikając na niego __prawym przyciskiem myszy__ na liście duszków.
2. __Zmień rozmiar każdego ducha__, aby każdy z nich był innej wielkości.
3. Zmień __zmienną "prędkość"__ każdego ducha, aby każdy z nich latał z inną prędkością.
4. Poprzesuwaj duchy po ekranie, aby nie latały wszystkie obok siebie.

##Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy masz na ekranie kilka duchów, latających od brzegu do brzegu ekranu, które niespodziewanie pojawiają się i znikają? Czy duchy znikają po kliknięciu na nie?

## Zapisz swój projekt. {.save}

##Rzeczy do spróbowania?

1. __Jaka ilość duchów będzie najlepsza dla naszej gry?__
2. __Czy możesz sprawić, aby duchy wyglądały inaczej? Możesz zmienić ich kostium albo wybrać zupełnie inny wygląd?__
3. __Czy możesz zmienić liczbę punktów, które dostaje się za różne duchy? Na przykład najszybszy (i najmniejszy) duch mógłby być wart 10 punktów.__

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__

Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
