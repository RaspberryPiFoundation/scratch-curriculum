---
title: Fajerwerki
materials: "*.sb"
pdf: "03 Fajerwerki.pdf"
notes: "03 Fajerwerki - Informacje.md"
notes_pdf: "03 Fajerwerki - Informacje.pdf"
layout: project
---

# Wstęp {.intro}
Ta interaktywna zabawka pokazuje wybuchające fajerwerki i odtwarza dźwięk wybuchu przy każdym kliknięciu.

![screenshot](fajerwerki.png)

# Krok 1: Stwórz rakietę, która leci w kierunku kursora myszki {.activity}
__Zaimportujmy wszystkie obrazki potrzebne do gry__

## Zadania do wykonania {.check}

+ Rozpocznij nowy projekt w Scratchu. Usuń kota, klikając na nim prawym przyciskiem myszki i wybierając "usuń".
+ Zmień tło na __city with water__ z kategorii __Na zewnątz__.
+ Użyj przycisku `Wybierz nowego duszka z pliku` {.blockgrey}, aby dodać rakietę. Otwórz katalog __Zasoby__ i wybierz plik __rakieta.png__. Zmień nazwę duszka na "Rakieta".
+ Spraw, aby rakieta zniknęła po wciśnięciu zielonej flagi.

Teraz sprawimy, aby po klinięciu rakieta poleciała w kierunku kursora myszki.

+ Dodaj blok `kiedy klawisz spacja naciśnięty` {.blockbrown} do skryptu, a pod nim dodaj skrypt pokazujący ponownie rakietę i sprawiający, że poleci ona w kierunku kursora myszy.

    ```blocks
        kiedy kliknięto zieloną flagę
        ukryj

        kiedy klawisz [spacja v] naciśnięty
        pokaż
        leć przez (1) s do x: (x myszy) y: (y myszy)
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__

Czy rakieta pojawia się na ekranie i leci w kierunku kursora myszy?
Co się dzieje, kiedy poruszysz myszą i wciśniesz spację ponownie?

## Zadania do wykonania {.check}

+ Fajerwerki nie latają na boki, więc upewnijmy się, że za każdym razem rakieta leci prosto do góry. Zanim pokażemy rakietę na ekranie, użyjmy bloku `idź do` {.blockblue}, aby ustawić ją pionowo na dole ekranu.

    ```blocks
        kiedy kliknięto zieloną flagę
        ukryj

        kiedy klawisz [spacja v] naciśnięty
        idź do x: (x myszy) y: (-200)
        pokaż
        leć przez (1) s do x: (x myszy) y: (y myszy)
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__

Czy rakieta leci w kierunku kursora z samego dołu ekranu?
Co się dzieje, kiedy przesuniesz kursor w bok i wciśniesz spację ponownie?

## Zadania do wykonania {.check}

+ Pora zamienić naciśnięcie klawisza spacji na kliknięcie klawiszem myszki. Aby to zrobić, "owińmy" nasz skrypt w blok `zawsze` {.blockyellow}, `jeżeli wciśnięty klawisz myszy` {.blockyellow}, a następnie zastąpmy blok `kiedy klawisz spacja naciśnięty` {.blockbrown} blokiem `kiedy kliknięto zieloną flagę` {.blockbrown}. Pamiętaj, żeby na początku gry rakieta była zawsze ukryta.

    ```blocks
        kiedy kliknięto zieloną flagę
        ukryj
        zawsze
            jeżeli <wciśnięty klawisz myszy?> to
                idź do x: (x myszy) y: (-200)
                pokaż
                leć przez (1) s do x: (x myszy) y: (y myszy)
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę, a następnie kliknij na scenie. Kliknij jeszcze raz w innym miejscu.__

## Rzeczy do spróbowania {.try}
+ Spróbuj zmienić prędkość rakiety: niech niektóre lecą szybciej, a inne wolniej.
+ Spróbuj zmienić cel rakiety, zanim zacznie lecieć w stronę myszy. (Tak aby leciała lekko po łuku.)

## Zapisz swój projekt. {.save}

# Krok 2: Spraw, aby rakieta wybuchła {.activity}

## Zadania do wykonania {.check}

+ Pierwszym zadaniem dla nas będzię dodanie odgłosu huku tuż przed wylotem rakiety oraz schowanie jej, gdy doleci do celu. Aby zaimportować odgłos wybuchu, przejdź do zakładki "Dźwięki", kliknij `Wgraj dźwięk z pliku` {.blockgrey} i wybierz plik __bum__ z katalogu __Zasoby__.

    ```blocks
        kiedy kliknięto zieloną flagę
        ukryj
        zawsze
            jeżeli <wciśnięty klawisz myszy?> to
                idź do x: (x myszy) y: (-200)
                zagraj dźwięk [bum v]
                pokaż
                leć przez (1) s do x: (x myszy) y: (y myszy)
                ukryj
    ```

+ Następnie nadajmy komunikat eksplozji rakiety. Odbierzemy go troszkę później.

    ```blocks

        kiedy kliknięto zieloną flagę
        ukryj
        zawsze
            jeżeli <wciśnięty klawisz myszy?> to
                idź do x: (x myszy) y: (-200)
                zagraj dźwięk [bum v]
                pokaż
                leć przez (1) s do x: (x myszy) y: (y myszy)
                ukryj
                nadaj [wybuch v]
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Upewnij się, że rakieta odtwarza dźwięk i chowa się po osiągnięciu celu.

## Zadania do wykonania {.check}

+ Dodaj nowego duszka z pliku __fajerwerki1.png__ z katalogu __Zasoby__.
+ Kiedy nowy duszek odbierze komunikat o wybuchu, powinien się ukryć i przesunąć w miejsce, w którym jest rakieta – użyj do tego bloku `idź do` {.blockblue}. Następnie powinien się pokazać w nowym miejscu i zniknąć ponownie sekundę później.

    ```blocks

        kiedy otrzymam [wybuch v]
        ukryj
        idź do [Rakieta v]
        pokaż
        czekaj (1) s
        ukryj
    ```

## Przetestuj swój projekt {.flag}
__Wystrzel następną rakietę.__

Czy rakieta została zastąpiona obrazkiem wybuchu?
Co się dzieje, kiedy przytrzymasz wciśnięty przycisk myszy i przesuwasz kursor? (Nie martw się, naprawimy ten problem później).

## Zapisz swój projekt. {.save}

# Krok 3: Spraw, aby każda eksplozja była wyjątkowa {.activity}

## Zadania do wykonania {.check}

+ Teraz sprawmy, aby każdy wybuch był inny. Skorzystaj z bloku `ustaw efekt kolor` {.blockpurple} i każ mu wybierać losowy kolor z listy od __1__ do __200__ przed pokazaniem wybuchu.

    ```blocks

        kiedy otrzymam [wybuch v]
        ukryj
        ustaw efekt [kolor v] na (losuj od (1) do (200))
        idź do [Rakieta v]
        pokaż
        czekaj (1) s
        ukryj
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy każda eksplozja ma inny kolor?

## Zadania do wykonania {.check}

+ Dodajmy kilka różnych rodzajów eksplozji. Zaimportuj pliki __fajerwerki2.png__ i __fajerwerki3.png__ z katalogu __Zasoby__ jako nowe kostiumy i dodaj przełączanie między nimi dla każdej rakiety tuż przed jej pokazaniem się.

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy każda rakieta wybucha w inny sposób i ma inny kolor?

## Zadania do wykonania {.check}

+ Na koniec sprawmy, aby każda eksplozja powiększała się w miarę upływu czasu, a nie po prostu pojawiała się na ekranie. Zamiast czekać sekundę, ustaw rozmiar duszka na __5%__ zanim zostanie pokazany, a potem, jak już będzie widoczny, skorzystaj z bloku `powtórz` {.blockbrown}, aby zwiększyć jego rozmiar o __2 pięćdziesiąt razy__.

    ```blocks

        kiedy otrzymam [wybuch v]
        ukryj
        ustaw efekt [kolor v] na (losuj od (1) do (200))
        idź do [Rakieta v]
        ustaw rozmiar na (5) %
        pokaż
        powtórz (50) razy
            zmień rozmiar o (2)
        koniec
        ukryj
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy wybuch rakiety powiększa się w miarę upływu czasu?

## Rzeczy do spróbowania {.try}
+ Spróbuj sprawić, aby każdy wybuch był bardziej wyjątkowy, zmieniając jego rozmiar i szybkość wzrostu każdej eksplozji.

## Zapisz swój projekt. {.save}

# Krok 4: Naprawiamy problem z nadawaniem {.activity}

Pamiętasz błąd, który pojawił się wcześniej przy poruszaniu kursora myszy, gdy przycisk myszy jest wciśnięty?
Dzieje się tak z dlatego, że rakieta nadaje komunikat o wybuchu i natychmiast powtarza pętlę "jeżeli", która z kolei nadaje kolejny komunikat o wybuchu, zanim ten poprzedni skończył się wyświetlać.

## Zadania do wykonania {.check}

+ Aby to naprawić, możemy zastąpić blok `nadaj` {.blockbrown} blokiem `nadaj i czekaj` {.blockbrown}, przez co pętla nie powtórzy się, dopóki wybuch się nie skończy.

    ```blocks

        kiedy kliknięto zieloną flagę
        ukryj
        zawsze
            jeżeli <wciśnięty klawisz myszy?> to
                idź do x: (x myszy) y: (-200)
                zagraj dźwięk [bum v]
                pokaż
                leć przez (1) s do x: (x myszy) y: (y myszy)
                ukryj
                nadaj [wybuch v] i czekaj
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę, przytrzymaj przycisk myszy i przesuń kursor po ekranie.__

Czy obrazek eksplozji pojawia się teraz w odpowiednim miejscu i we właściwym czasie?

## Zapisz swój projekt. {.save}

**Brawo! To by było na tyle, teraz możesz cieszyć się swoją grą!**

Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu **Udostępnij**.

