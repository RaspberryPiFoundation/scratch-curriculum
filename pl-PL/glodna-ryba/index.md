---
title: Głodna ryba
level: Poziom 2
materials: ["*.sb", "Zasoby/*.mp3", "Zasoby/*.png"]
pdf: "05 Glodna ryba.pdf"
notes: "05 Glodna ryba - Informacje.md"
notes_pdf: "05 Glodna ryba - Informacje.pdf"
---

# Wstęp {.intro}

Zrobimy grę w karmienie ryb! Będziesz kierować dużą głodną rybą pływającą po morzu w taki sposób, aby udało jej się zjeść wszystkie rozgwiazdy.

![screenshot](glodna-ryba.png)

# Krok 1: Stwórz duszka, który goni kursor myszki {.activity}
__Dodajmy rybę, która pływa po morzu!__

## Zadania do wykonania {.check}

* Zacznij nowy projekt w Scratchu.
* Zaznacz Scenę, a następnie przejdź do karty z ustawieniami tła. Zaimportuj tło **underwater3** z katalogu **Natura**. Usuń tło **backdrop1**.
* Zmień nazwę duszka z Sprite1 na "Głodna Ryba" klikając na niebieską ikonkę **i**.
* Zaimportuj kostium Głodnej Ryby wybierając z katalogu Zasoby plik **ryba-paszcza-otwarta.png***, a następnie usuń istniejący **costume1** i **costume2**.
* Kliknij ponownie na niebieską ikonkę **i** i upewnij się, że duszek może obracać się tylko w prawo i lewo.
* Dodaj skrypt, który każe rybie pływać w kierunku kursora myszki:

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            ustaw w stronę [wskaźnik myszy v]
            przesuń o (3) kroków
    ```

## Przetestuj swój projekt {.flag}

__Wciśnij zieloną flagę.__
Poruszaj kursorem myszy po morzu. Czy ryba pływa za nim?
Co się dzieje, jeżeli nie ruszasz kursorem i ryba go złapie? Jak to wygląda? Dlaczego tak się dzieje?

## Zadania do wykonania {.check}

* Możesz zapobiec takiemu motaniu się ryby, jeżeli każesz jej ruszać się tylko wtedy, kiedy nie jest za blisko kursora (w sekcji `Czujniki` {.blocklightblue} znajdziesz blok `odległość do` {.blocklightblue}).

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            jeżeli <(odległość do [wskaźnik myszy v]) > (10)> to
                ustaw w stronę [wskaźnik myszy v]
                przesuń o (3) kroków
    ```

## Przetestuj swój projekt {.flag}

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try}
Jeżeli chcesz, możesz zmienić liczby w skrypcie. W jaki sposób zmienia to sposób poruszania się Głodnej Ryby? Zmień odległość na jakiąś dużą liczbę (np. 100) albo jakąś bardzo małą (np. 1). Zmień ilość kroków na coś dużego (np. 20) lub małego (np. 1 lub nawet 0). Co się dzieje?


# Krok 2: Dodaj rozgwiazdę {.activity}

## Zadania do wykonania {.check}

* Stwórz nowego duszka korzystając z kostiumu **Zwierzęta/Starfish**.
* Zmniejsz nowego duszka (narzędzie do zmniejszania znajduje się nad Sceną).
* Dodaj skrypt, który kieruje pływającą rozgwiazdą. Chcemy, aby ruszała się losowo, więc byłoby dobrze, aby najpierw ruszała się trochę do przodu, a potem skręciła albo w lewo, albo w prawo, a potem zaczęła się ruszać od nowa.

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            przesuń o (2) kroków
            obróć @ o (losuj od (-20) do (20)) stopni
            jeżeli na brzegu, odbij się
    ```

## Przetestuj swój projekt {.flag}

__Wciśnij zieloną flagę__ i popatrz, jak rozgwiazda porusza się po ekranie. Czy pływa tak jak trzeba? Czy wygląda to realistycznie?

__Teraz ryba i rozgwiazda nie interesują się sobą. Zajmiemy się tym w następnym kroku.__

## Zapisz swój projekt {.save}

## Rzeczy do spróbowania {.try}

* Zmień liczby w bloku `losuj od .. do ...` {.blockgreen} oraz odległość, o jaką porusza się rozgwiazda. W jaki sposób te zmiany wpływają na sposób poruszania się?
* Co robi blok `jeżeli na brzegu, odbij się` {.blockblue}? Usuń go i zobacz co się stanie.


# Krok 3: Głodna ryba łapie rozgwiazdę {.activity}

__Chcemy, aby ryba zjadła rozgwiazdę!__ Jak tylko ryba złapie żyjątko, muszą stać się dwie rzeczy:
* Ryba musi zamknąć paszczę z głośnym "mlask!"
* rozgwiazda musi zniknąć i pojawić się chwilę później gdzie indziej

## Zadania do wykonania {.check}

* Na początek sprawmy, aby rozgwiazda znikała po dotknięciu ryby i po 3 sekundach pojawiała się gdzie indziej. Użyjemy bloku `dotyka` {.blocklightblue}, aby sprawdzić, czy rozgwiazda jest w kontakcie z rybą.

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            przesuń o (2) kroków
            obróć @ o (losuj od (-20) do (20)) stopni
            jeżeli na brzegu, odbij się
            jeżeli <dotyka [Głodna Ryba v]?> to
                ukryj
                czekaj (3) s
                pokaż
    ```

## Przetestuj swój projekt {.flag}
__Spróbuj złapać rozgwiazdę – czy widzisz jakieś problemy?__ Zauważ, że rozgwiazda znika bez względu na to, z której strony dotknie rybę. Poza tym, jeżeli ryba się nie rusza, to po 3 sekundach może od razu zjeść rozgwiazdę – to jest trochę niefajne!

## Zadania do wykonania {.check}

* Co możemy zrobić, aby upewnić się, że rozgwiazda znika tylko wtedy, gdy ryba dotknie jej paszczą? Możemy skorzystać z czujnika `dotyka koloru` {.blocklightblue} i sprawdzać, czy rozgwiazda dotyka niebieskich zębów ryby! Aby to zrobić, zamień blok `dotyka` {.blocklightblue} na `dotyka koloru` {.blocklightblue}, kliknij kwadracik z kolorem, a gdy kursor myszy się zmieni, kliknij na zębach ryby.
* Następnie możemy sprawić, aby rozgwiazda przesuwała się w losowe miejsce na ekranie przed ponownym pojawieniem. Możemy użyć do tego bloku `idź do` {.blockblue} i użyć losowych wartości dla **x** i **y**.

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            przesuń o (2) kroków
            obróć @ o (losuj od (-20) do (20)) stopni
            jeżeli na brzegu, odbij się
            jeżeli <dotyka koloru [#FFFFFF]?> to
                ukryj
                czekaj (3) s
                idź do x:(losuj od (-220) do (220)) y:(losuj od (-170) do (170))
                pokaż
    ```

## Przetestuj swój projekt {.flag}

Spróbuj złapać rozgwiazdę jeszcze raz – czy znika ona tylko wtedy, kiedy dotknie zębów ryby? I czy pojawia się w losowym miejscu na ekranie zamiast od razu tam, gdzie została zjedzona?

## Zadania do wykonania {.check}

* Ryba musi wiedzieć, kiedy zjadła rozgwiazdę, aby mogła wydać dźwięk i zmienić kostium. Aby to zrobić, musimy najpierw `nadać` {.blockbrown} sygnał, że rozgwiazda została zjedzona.

    ```blocks
        kiedy kliknięto zieloną flagę
        zawsze
            przesuń o (2) kroków
            obróć @ o (losuj od (-20) do (20)) stopni
            jeżeli na brzegu, odbij się
            jeżeli <dotyka koloru [#FFFFFF]?> to
                nadaj [masz mnie v]
                ukryj
                czekaj (3) s
                idź do x:(losuj od (-220) do (220)) y:(losuj od (-170) do (170))
                pokaż
    ```

__Teraz chcemy, aby ryba odpowiedziała na to głośnym zamknięciem paszczy.__

## Zadania do wykonania {.check}

* Dodaj Głodnej Rybie drugi kostium importując go z pliku **Zasoby/ryba-paszcza-zamknieta.png". Dodaj też dźwięk z pliku **Zasoby/siorbanie.mp3**.
* Następnie dodaj skrypt do Głodnej Ryby, który odpowiada na wiadomość nadaną przez rozgwiazdę. Skrypt powinien zagrać odgłos **siorbania** i `zamienić kostium` {.blockpurple} ryby na ten z zamkniętą paszczą, a następnie poczekać chwilę i wrócić do pierwszego kostiumu.

    ```blocks
        kiedy otrzymam [masz mnie v]
        zagraj dźwięk [siorbanie v]
        powtórz (2) razy
            zmień kostium na [ryba-paszcza-zamknieta v]
            czekaj (0.5) s
            zmień kostium na [ryba-paszcza-otwarta v]
    ```

__Skoro nasza Głodna Ryba jest gotowa jeść, wypełnijmy ocean jedzeniem. Kliknij na rozgwieździe prawym przyciskiem myszy i zduplikuj ją kilka razy.__

## Przetestuj swój projekt {.flag}
Kliknij zieloną flagę.
Czy Głodna Ryba zjada swoje ofiary? Czy potrafi zjeść każdą rozgwiazdę?

## Zapisz swój projekt. {.save}

## Rzeczy do przemyślenia
Dlaczego musimy dodać blok `pokaż` {.blockpurple} na początku skryptu każdej rozgwiazdy? Pomyśl, co by się stało, gdyby gra została zatrzymana zanim zjedzona rozgwiazda ponownie pojawi się na ekranie. Co by się stało po uruchomieniu gry?

__Brawo! Udało Ci się skończyć podstawową wersję gry. Jest jeszcze kilka rzeczy, które możesz zmienić w grze. Pora na wyzwania!__


## Wyzwanie 1: Spraw, aby rozgwiazdy poruszały się inaczej {.challenge}

Póki co wszystkie rozgwiazdy poruszają się tak samo.

__Spróbuj zmienić sposób w jaki porusza się jedna z rozgwiazd.__

__Podpowiedź:__ Postaraj się nie spędzić na tym zadaniu zbyt dużo czasu. Warto również spojrzeć na inne wyzwania!

__Wybierz jedną rozgwiazdę, nad którą będziesz pracować.__
Jeżeli ma ona ten sam kostium co inne, zmień jego kolor używając bloku `ustaw efekt kolor na` {.blockpurple}. W ten sposób będziesz łatwo widzieć, nad którą rozgwiazdą pracujesz.

Spraw, aby ta rozgwiazda poruszała się wolniej od innych.

__Podpowiedź:__ Spójrz na blok `przesuń o 2 kroków` {.blockblue}.


## Przetestuj swój projekt {.flag}
Czy rozgwiazda porusza się wolniej? Czy gra jest teraz lepsza?
Jeżeli udało ci się to zrobić, __wybierz inną rozgwiazdę i spraw, aby poruszała się szybciej od innych.__

Czy rozgwiazdy poruszają się naturalnie? Czy gra jest jeszcze lepsza po tych zmianach?

__Podpowiedź:__ Jeżeli rozgwiazdy pływają w kółko, zmień wartości z bloku `losuj od ... do ...` {.blockgreen}.

A może spróbujesz zmienić zachowanie rozgwiazd, tak aby każda poruszała się inaczej? Wykorzystaj wprowadzone poprzednio zmiany.

Czy te zmiany sprawiły, że gra jest jeszcze lepsza? Czy gra podoba ci się bardziej, jest trudniejsza czy łatwiejsza? Może któraś konkretna zmiana podoba ci się najbardziej?

## Zapisz swój projekt {.save}

## Wyzwanie 2: Spraw, aby rozgwiazdy unikały głodnej ryby. {.challenge}

rozgwiazdy w tej grze nie zachowują się zbyt mądrze: po prostu pływają w kółko i dają się zjeść rybie. Prawdziwa rozgwiazda na pewno próbowała by uciec od drapieżnika!

__Spróbujmy sprawić, aby jedna z rozgwiazd uciekała przed Głodną Rybą__

W Scratchu nie ma bloku, który powiedziałby ci, w którym kierunku porusza się inny duszek. Ale możesz sprawić, aby duszek zwrócił się w kierunku innego duszka, a potem odwrócił się od niego plecami. Bloki, których będziesz potrzebować, znajdują się w palecie `Ruch` {.blockblue}.

Wykorzystując ten pomysł, __spraw, aby jedna z rozgwiazd zawsze była odwrócona do Głodnej Ryby plecami__. Może spróbujesz sprawić, aby się trzęsła jak będzie uciekać?

## Przetestuj swój projekt {.flag}
Czy teraz trudniej jest złapać rozgwiazdę? Czy gra jest teraz lepsza?

## Zapisz swój projekt {.save}

## Wyzwanie 3: Dodaj punkty {.challenge}

Ale zjadanie rozgwiazd to nie wszystko. Skąd będziesz wiedzieć, czy umiesz grać w tę grę lepiej niż inni gracze?
__Potrzebujesz w jakiś sposób liczyć ile rozgwiazd udało Ci się zjeść__. Już robiliśmy coś podobnego wcześniej.

Gdzie należy dodać blok, który będzie zmieniał liczbę punktów?

Upewnij się, żeby punkty przestawiały się na zero przy rozpoczęciu nowej gry. Gdzie trzeba dodać ten blok?

## Przetestuj swój projekt {.flag}
Czy jak zaczynasz nową grę, to liczba punktów jest równa zero? Czy dostajesz punkt za każdą zjedzoną rozgwiazdę?

## Zapisz swój projekt. {.save}

## Wyzwanie 4: Dodaj zegar {.challenge}

__Ograniczmy czas, w którym możesz zjadać rozgwiazdy.__ Jak wiele rozgwiazd uda ci się zjeść w ciągu 30 sekund?

Jeżeli nie masz pomysłu, jak to zrobić, spróbuj przypomnieć sobie, jak to robiliśmy wcześniej. Na początek niech gra trwa 30 sekund.

## Przetestuj swój projekt {.flag}
Czy kiedy zaczynasz grę, zegar wskazuje 30?

Czy zegar poprawnie odlicza czas?

Czy udaje Ci się zjeść jakieś rozgwiazdy w tym czasie?

Czy gra się zatrzymuje po upływie czasu?

## Zapisz swój projekt. {.save}

## Wyzwanie 5: Zdobądź dodatkowe punkty {.challenge}
Zdobywaj dodatkowe punkty, jeżeli uda Ci się zjeść 3 rozgwiazdy na raz! W jaki sposób możesz sprawdzić, ile rozgwiazd udało Ci się zjeść?

__Podpowiedź:__ Jeden ze sposobów, w jaki możesz to zrobić, to __użyć zmiennej, która policzy jak wiele rozgwiazd pływa wokoło ryby__.

## Zapisz swój projekt. {.save}

## Wyzwanie 6: Zmień cel gry: rozgwiazda musi przeżyć! {.challenge}
Czasami super pomysły przychodzą do głowy, jeżeli spróbujesz zrobić coś na odwrót.

__Zmień grę w ten sposób, żeby zamiast sterować Głodną Rybą, która próbuje zjeść rozgwiazdy, sterowało się rozgwiazdą otoczoną wieloma Głodnymi Rybami__. Jak długo uda jej się przetrwać, zanim zostanie zjedzona?

## Zapisz swój projekt. {.save}

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
