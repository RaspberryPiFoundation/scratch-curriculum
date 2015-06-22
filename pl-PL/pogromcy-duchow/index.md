---
title: Pogromcy duchów
level: Poziom 1
materials: "*.sb"
pdf: "02 Pogromcy duchow.pdf"
notes: "02 Pogromcy duchow - Informacje.md"
notes_pdf: "02 Pogromcy duchow - Informacje.pdf"
layout: project
---

# Wstęp {.intro}

Ten projekt bazuje na popularnej angielskiej grze zwanej Whack-A-Mole: zdobywasz punkty klikając w duchy, które pojawiają się na ekranie. Celem gry jest zdobycie jak największej liczby punktów w ciągu 30 sekund.

![screenshot](pogromcy-duchow.png)

# Krok 1: Stwórz latającego ducha {.activity}

## Zadania do wykonania {.check}

+ __Stwórz nowy projekt.__
+ __Usuń duszka kota__ i zastąp tło lasem (woods) z katalogu __Natura__.
+ Kliknij przycisk `Wybierz nowego duszka z biblioteki` {.blockgrey} i dodaj ducha do projektu (znajdź kostium __Fikcja/ghost2-b__).

__Teraz sprawmy, aby duch zaczął latać__

+ Dodaj `zmienną` {.blocklightgrey} tylko dla tego duszka i nazwij ją `prędkość` {.blockorange}.
Nowa zmienna powinna pojawić się na __Scenie__ jako __"Ghost2: prędkość"__.
Jeżeli widzisz tam tylko "prędkość", usuń zmienną i stwórz ją na nowo, tylko tym razem wybierz opcję "Tylko dla tego duszka".
Odznacz "prędkość" w __panelu Dane__, aby nie było jej widać na Scenie. Ta zmienna będzie kontrolować prędkość lotu naszego ducha. Korzystamy ze zmiennej, aby móc później zmieniać prędkość lotu ducha.
+ Chcemy, aby duch zaczął latać zaraz po rozpoczęciu gry. __Stwórz dla niego poniższy skrypt__:

    ```blocks
        kiedy kliknięto zieloną flagę
        ustaw [prędkość v] na [5]
        zawsze
            przesuń o (prędkość) kroków
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę__ i zobacz, co robi duch. Dlaczego utknął na brzegu ekranu?

## Zadania do wykonania {.check}

+ Aby duch nie zatrzymywał się na brzegu ekranu, musimy sprawić, aby zawracał za każdym razem, gdy doleci do brzegu ekranu. Dodajmy blok `jeżeli na brzegu, odbij się` {.blockblue} poniżej bloku
`przesuń o ` {.blockblue}`prędkość` {.blockorange}` kroków` {.blockblue} w skrypcie ducha.

    ```blocks
        kiedy kliknięto zieloną flagę
        ustaw [prędkość v] na [5]
        zawsze
            przesuń o (prędkość) kroków
            jeżeli na brzegu, odbij się
    ```

+ Aby duch nie obracał się do góry nogami, wybierz opcję `Styl obrotów: prawo-lewo` {.blockgrey} w ustawieniach tego duszka.

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__
Czy duch lata od brzegu do brzegu ekranu?

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
+ __Spróbuj zmienić wartość zmiennej prędkość, aby sprawić, żeby duch latał szybciej lub wolniej.__
+ __Co zrobić, aby duch leciał coraz szybciej w trakcie gry?__
(Jest to troszkę skomplikowane, więc nie przejmuj się, jeżeli jeszcze nie wiesz jak to zrobić. Podpowiemy Ci troszkę później jak to zrobić.)

# Krok 2: Spraw, aby duch losowo pojawiał się i znikał {.activity}

Aby gra była ciekawsza, spróbujemy sprawić, aby duch losowo pojawiał się i znikał. Będzie nam do tego potrzebny kolejny skrypt, który działa w tym samym czasie co ten odpowiedzialny za poruszanie duchem. Nowy skrypt powinien niespodziewanie ukryć ducha i po jakimiś czasie znowu pokazać go na ekranie (i robić to cały czas w trakcie gry).

## Zadania do wykonania {.check}

__Dodajmy duchowi poniższy skrypt:__

```blocks
    kiedy kliknięto zieloną flagę
    zawsze
        ukryj
        czekaj (losuj od (2) do (5)) s
        pokaż
        czekaj (losuj od (3) do (5)) s
```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy duch lata od brzegu do brzegu ekranu oraz losowo pojawia się i znika?

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
+ __Spróbuj zmienić wartość liczb, które użyliśmy do ukrywania i pojawiania się ducha. Co się stanie, jeżeli wybierzemy bardzo duże albo bardzo małe liczby?__
(Czy pomoże Ci to sprawić, aby duch latał coraz szybciej?)

# Krok 3: Spraw, aby duch znikał, gdy na niego klikniesz {.activity}

Aby zamienić ten projekt w grę, musimy dać graczom coś do zrobienia. Niech klikają w ducha, aby zniknął. Chcemy, aby po kliknięciu w ducha było słychać jakiś dźwięk, a sam duch znikał z ekranu.

## Zadania do wykonania {.check}

+ W zakładce __Dźwięki__ zaimportuj z biblioteki dźwięk __fairydust__ z katalogu __Elektroniczne__.

+ __Dodajmy duchowi poniższy skrypt__:

    ```blocks
        kiedy duszek kliknięty
        ukryj
        zagraj dźwięk [fairydust v]
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy ducha znika i wydaje dźwięk, gdy go klikniesz?

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
+ __Zapytaj osoby prowadzącej zajęcia, czy możesz spróbować nagrywać własny dźwięk i użyć go w swoim projekcie.__

# Krok 4: Dodaj punkty i zegar {.activity}

Mamy już ducha, więc wykorzystamy go do stworzenia własnej gry! Zaczniemy liczyć punkty za każde kliknięcie na ducha. Dodamy też do gry limit czasu. W tym celu użyjemy dwóch nowych zmiennych.

## Zadania do wykonania {.check}

+ Stwórz nową `zmienną` {.blockgrey} dla każdego duszka i nazwij ją __wynik__. Zmieńmy skypt ducha tak, aby przy każdym kliknięciu wartość tej zmiennej zwiększała się o jeden punkt.

    ```blocks
        kiedy duszek kliknięty
        ukryj
        zagraj dźwięk [Fairydust v]
        zmień [wynik v] o (1)
    ```

+ Kliknij na __Scenę__, stwórz __nową zmienną__ i nazwij ją __czas__. Dodaj nowy skrypt uruchamiany kliknięciem flagi, który ustawia `czas` {.blockorange} na __30__ oraz wynik na __0__. Skorzystaj z bloku `powtarzaj aż` {.blockyellow}, aby odczekać sekundę i zmniejszyć wartość `czasu` {.blockorange} o jeden. Akcja powinna powtarzać się dopóki licznik czasu nie dojdzie do zera. Wtedy to zakończymy grę używając bloku `zatrzymaj wszystko` {.blockyellow}.

    ```blocks
        kiedy kliknięto zieloną flagę
        ustaw [czas v] na (30)
        ustaw [wynik v] na (0)
        powtarzaj aż <(czas) = [0]>
            czekaj (1) s
            zmień [czas v] o (-1)
        koniec
        zatrzymaj [wszystko v]
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
+ __Jak można sprawić, aby duch latał coraz szybciej?__

__Udało ci się skończyć podstawową wersję gry, ale ciągle są rzeczy, które możesz zmienić w grze. Mamy dla Ciebie wyzwanie!__

## Wyzwanie: Dodaj więcej duchów {.challenge}

Gra z jednym duchem jest super, ale co jeżeli dodamy ich więcej. Na pewno gra będzie jeszcze lepsza! __Dodajmy kolejne latające duchy do naszej gry.__

+ Zduplikuj ducha klikając na niego __prawym przyciskiem myszy__ na liście duszków.
+ __Zmień rozmiar każdego ducha__, aby każdy z nich był innej wielkości.
+ Zmień __zmienną "prędkość"__ każdego ducha, aby każdy z nich latał z inną prędkością.
+ Poprzesuwaj duchy po ekranie, aby nie latały wszystkie obok siebie.

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy masz na ekranie kilka duchów, latających od brzegu do brzegu ekranu, które niespodziewanie pojawiają się i znikają? Czy duchy znikają po kliknięciu na nie?

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
+ __Jaka liczba duchów będzie najlepsza dla naszej gry?__
+ __Czy możesz sprawić, aby duchy wyglądały inaczej? Możesz zmienić ich kostium albo wybrać zupełnie inny wygląd?__
+ __Czy możesz zmienić liczbę punktów, które dostaje się za różne duchy? Na przykład najszybszy (i najmniejszy) duch mógłby być wart 10 punktów.__

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__

Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
