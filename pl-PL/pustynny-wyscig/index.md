---
title: Pustynny wyścig
materials: "*.sb"
pdf: "06 Pustynny wyscig.pdf"
notes: "06 Pustynny wyscig - Informacje.md"
notes_pdf: "06 Pustynny wyscig - Informacje.pdf"
layout: project
---

# Wstęp {.intro}

Jest to gra dla dwóch graczy, podczas której papuga i lis ścigają się po pustyni. Gracze kierują swoją postacią wciskając szybko klawisz na klawiaturze. Zwierzę, które pierwsze dotrze do krawędzi ekranu, wygrywa.

![screenshot](Pustynny-wyscig.png)

# Krok 1: Stwórz scenę i dodaj duszki {.activity}

## Zadania do wykonania {.check}

+ Kliknij na scenę i dodaj tło z pustynią z katalogu **Natura**.
+ Dodaj nowego duszka i wybierz kostium lwa z katalogu ze zwierzętami.
+ Dodaj kolejnego duszka i wybierz kostium papugi. `Zmniejsz` {.blocklightgrey} ją tak, aby była mniej więcej rozmiarów lwa.


# Krok 2: Spraw, aby lew i papuga się poruszały {.activity}

Chcemy, aby duszki poruszały się kiedy naciśniesz klawisz.

## Zadania do wykonania {.check}

+ Na początek wybierzmy lwa i ustawmy, aby poruszał się o 4 kroki po wciśnięciu klawisza **'L'**
    
    ```blocks
        kiedy klawisz [l v] naciśnięty
        przesuń o (4) kroków
    ```

+ Teraz pora na papugę. Ustawmy, aby przesuwała się o 4 kroki po wciśnięciu klawisza 'A'.
    
    ```blocks
        kiedy klawisz [a v] naciśnięty
        przesuń o (4) kroków
    ```

## Przetestuj swój projekt {.flag}
__Wciśnij zieloną flagę__ 
Czy lew i papuga poruszają się po ekranie, gdy wciskasz 'A' i 'L'?

## Zapisz swój projekt. {.save}


# Krok 3: Rozpoczęcie wyścigu {.activity}

Aby móc określić później, kto wygrał, musimy najpierw wiedzieć, kiedy wyścig się rozpoczął. __Dodajmy przycisk Start.__

## Zadania do wykonania {.check}

+ Dodaj nowego duszka z pliku. Wybierz przycisk z katalogu "things".
+ Przejdź do edycji kostiumu, napisz na nim 'Start' i wciśnij OK. Przesuń duszka na środek sceny.
+ Dodaj do niego skrypt, który pokazuje przycisk, kiedy gra jest uruchomiona:

    ```blocks
        kiedy kliknięto zieloną flagę
        pokaż
    ```

+ Teraz chcemy, aby przycisk odliczał od 3 w dół i ogłaszał start wyścigu, a następnie się chował. Dodaj poniższy skrypt:

    ```blocks
        kiedy duszek kliknięty
        powiedz [3] przez (1) s
        powiedz [2] przez (1) s
        powiedz [1] przez (1) s
        powiedz [Start!] przez (1) s
        ukryj
    ```
    
## Przetestuj swój projekt {.flag}
__Wciśnij zieloną flagę__

Czy widzisz odliczanie po kliknięciu przycisku? Czy przycisk znika po zakończeniu odliczania?

## Zapisz swój projekt. {.save}

Chcemy, aby ścigający poruszali się tylko po rozpoczęciu wyścigu. Chcemy też wiedzieć, kiedy wyścig się zakończył. Będziemy potrzebować zmiennej do przechowywania tej informacji.

+ Dodaj zmienną do wszystkich duszków i nazwij ją `wyścig`{.blockorange}. Odznacz pole przy niej, aby nie było jej widać na scenie.
+ Teraz ustaw **wyścig** na **0**, kiedy gra się rozpocznie. Dodaj ten krok do skryptu przycisku:

    ```blocks
        kiedy kliknięto zieloną flagę
        pokaż
        ustaw [wyścig v] na (0)
    ```

+ Następnie ustaw zmienną **wyścig** zmieniała się na 1 po skończeniu odliczania.
+ Teraz musimy się upewnić, że lew i papuga mogą się ruszać tylko wtedy, kiedy zmienna wyścig jest ustawiona na 1. Kliknij na duszka z papugą. __Dodaj blok kontroli do skryptu__, który pozwala papudze ruszać się tylko wtedy, gdy zmienna __wyścig = 1__.

    ```blocks
        kiedy klawisz [a v] naciśnięty
        jeżeli <(wyścig) = [1]> to
            przesuń o (4) kroków
    ```
+ Zrób to samo dla lwa.

## Przetestuj swój projekt {.flag}
__Wciśnij zieloną flagę__

Czy lew i papuga ruszają się tylko po zakończeniu odliczania?

Teraz chcemy notować, kto wygrał wyścig i usuwać tę informację po zakończeniu gry, aby można było zacząć od nowa.

## Zapisz swój projekt. {.save}

# Krok 4: Kończenie wyścigu {.activity}

## Zadania do wykonania {.check}

+ Dodaj blok do skryptu papugi, który ustawia zmienną **wyścig** na 0, kiedy papuga dotknie brzegu ekranu.

    ```blocks
        kiedy klawisz [a v] naciśnięty
        jeżeli <(wyścig) = [1]> to
            przesuń o (4) kroków
            jeżeli <dotyka [krawędź v]?> to
                ustaw [wyścig v] na (0)
    ```

+ Teraz chcemy, aby papuga dała nam znać, czy wygrała. Nagraj nowy dźwięk dla papugi, który będzie odegrany, jeżeli papuga wygra. Przejdź na kartę `dźwięki` {.blocklightgrey} duszka i nagraj odgłos zwycięstwa!

+ Dodaj do skryptu komendę, która `zagra` {.blockpurple} to nagranie po wygranej:

    ```blocks
        kiedy klawisz [a v] naciśnięty
        jeżeli <(wyścig) = [1]> to
            przesuń o (4) kroków
            jeżeli <dotyka [krawędź v]?> to
                ustaw [wyścig v] na (0)
                zagraj dźwięk [nagranie1 v]
                powiedz [Papuga wygrała!] przez (3) s
    ```
+ Powtórz to samo dla lwa.

## Przetestuj swój projekt {.flag}
__Wciśnij zieloną flagę__

Czy działa rozpoczynanie wyścigu po wciśnięciu przycisku? Można się ścigać wciskając przyciski 'A' i 'L'?
Czy duszki dobrze ogłaszają, który z nich wygrał?

## Zapisz swój projekt. {.save}

# Krok 5: Restartowanie gry {.activity}

Po zakończeniu wyścigu musimy powiedzieć wszystkim duszkom, że to koniec i zresetować grę, aby mogła się zacząć od nowa.

__Duszek, który wygra, musi ogłosić swoje zwycięstwo.__

## Zadania do wykonania {.check}

+ Kliknij na papugę i dodaj do skryptu ogłaszanie końca wyścigu po wygranej.

    ```blocks
        kiedy klawisz [a v] naciśnięty
        jeżeli <(wyścig) = [1]> to
            przesuń o (4) kroków
            jeżeli <dotyka [krawędź v]?> to
                ustaw [wyścig v] na (0)
                zagraj dźwięk [nagranie1 v]
                powiedz [Papuga wygrała!] przez (3) s
                nadaj [koniec v]
    ```

+ Teraz musimy dodać nowy skrypt, który nasłuchuje, czy wyścig został zakończony i jeżeli tak, to przesuwa papugę na linię startu. 

    ```blocks
        kiedy otrzymam [koniec v]
        ustaw x na (-170)
    ```

+ Dodaj takie same skrypty dla lwa. W przypadku tego drugiego przetestuj inne wartości dla **x**, aby lew i papuga byli równo ustawieni na starcie.
+ Chcemy też, aby lew i papuga byli równo ustawieni po rozpoczęciu wyścigu, więc dodaj do obu duszków poniższy skrypt, który ustawia je równo po wciśnięciu flagi:

    ```blocks
        kiedy kliknięto zieloną flagę
        ustaw x na (-170)
    ```
+ Przejdź do duszka przycisku i dodaj skrypt, który go pokazuje po otrzymaniu komunikatu, że wyścig się zakończył.

## Przetestuj swój projekt {.flag}
__Wciśnij zieloną flagę__

Możesz się ścigać z kolegą, kiedy jedno z was kieruje papugą wciskając 'A', a drugie kieruje lwem wciskając 'L'?

## Zapisz swój projekt. {.save}

## Wyzwanie 1: Dodaj dopalacz {.challenge}

+ __Spróbuj dodać dopalacz__, który każdy duszek może użyć tylko raz podczas wyścigu. Dopalacz przesuwa postać w przód o __30 kroków__.
+ __Dodaj nowy kostium__ z płomieniem za każdym duszkiem i ustaw, aby się pokazywał, kiedy dopalacz zostanie użyty.
+ __Nagraj następny dźwięk__, który będzie odegrany po użyciu dopalacza.
    ```blocks
        kiedy klawisz [p v] naciśnięty
        jeżeli <<(wyścig) = [1]> and <(dopalacz) = [0]>> to
            zmień kostium na [parrot-dopalacz v]
            ustaw [dopalacz v] na [1]
            przesuń o (4) kroków
            jeżeli <dotyka [krawędź v]?> to
                ustaw (wyścig) na [0]
                zagraj dźwięk [nagranie1 v]
                powiedz [Papuga wygrała!] przez (3) s
                nadaj [koniec v]
    ```

## Przetestuj swój projekt {.flag}

## Zapisz swój projekt. {.save}

## Wyzwanie 2: Stwórz własne bloki, aby uprościć swój skrypt {.challenge}

Ten sam kod, który sprawdza, czy wyścig się skończył jest używany teraz w dwóch miejscach dla każdego duszka: kiedy duszek normalnie się porusza i kiedy rusza się z dopalaczem. Możemy uprościć nasz skrypt tworząc własny blok, w którym znajdą się bloki, które do tej pory powtarzały się w wielu miejscach.

+ Pokaż skrypt papugi.
+ Wybierz paletę `Więcej bloków` {.blocklightgrey} i kliknij na przycisk `Stwórz blok` {.blocklightgrey}.
+ Nadaj nowemu blokowi nazwę wpisując **"zakończony"** w różowe pole. Następnie kliknij OK.
+ Zauważ, że blok `definiuj zakończony` {.blockpurple} pojawił się w oknie ze skryptami. Przeciągnij go na puste miejsce tak, aby nie zasłaniał innych skryptów.
+ Odłącz blok `jeżeli`{.blockyellow}`dotyka krawędź?`{.blocklightblue}`to`{.blockyellow} i przeciągnij go podłączając pod blok `definiuj zakończony`{.blockputple}.
    ```blocks
        definiuj zakończony
            jeżeli <dotyka [krawędź v]?> to
                ustaw (wyścig) na [0]
                zagraj dźwięk [nagranie1 v]
                powiedz [Papuga wygrała!] przez (3) s
                nadaj [koniec v]
    
        kiedy klawisz [p v] naciśnięty
            jeżeli <<(wyścig) = [1]> and <(dopalacz) = [0]>> to
                zmień kostium na [parrot-dopalacz v]
                ustaw [dopalacz v] na [1]
                przesuń o (4) kroków
                zakończony
    ```

Czy możesz przeciągnąć blok `zakończony` {.blockpurple} z palety i użyć go jak każdego innego bloku?

Usuń pozostałe bloki `jeżeli`{.blockyellow}`dotyka krawędź?`{.blocklightblue}`to`{.blockyellow} z twojego skryptu i wstaw w ich miejsce twój blok `zakończony` {.blockputple}.

Czy to sprawiło, że twój kod jest teraz łatwiejszy do przeczytania? Czy możesz utworzyć podobny blok dla duszka lwa?

## Przetestuj swój projekt {.flag}

## Zapisz swój projekt. {.save}

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
