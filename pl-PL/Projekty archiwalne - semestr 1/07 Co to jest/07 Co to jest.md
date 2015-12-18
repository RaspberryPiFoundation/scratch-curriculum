---
title: Co to jest
level: Poziom 3
language: pl-PL
stylesheet: scratch
embeds: "*.png"
materials: "*.sb"
...

# Wstęp {.intro}

Na tablicy znajduje się zniekształcony obrazek. Musisz odgadnąć, co to jest, klikając na odpowiednią miniaturkę. Im szybciej zgadniesz, tym więcej punktów otrzymasz!

![screenshot](Co-to-jest.png)

# Krok 1: Wyświetl różne obrazki na tablicy {.activity}

__Chcemy pokazać na tablicy kilka różnych obrazków.__

## Zadania do wykonania {.check}

+ Stwórz nowy projekt Scratch i usuń duszka kota.
+ Kliknij na Scenę, a następnie na zakładkę Tła. Zaimportuj tło 'W pomieszczeniu/chalkboard'.
+ Zaimportuj nowego duszka i dodaj do niego kostium. Wybierz taki kostium, który Ci się podoba. Może znajdziesz coś ciekawego w katalogu 'Przedmioty'.
+ Umieść tego duszka na środku tablicy. Jeżeli trzeba, odpowiednio zwiększ lub zmniejsz jego rozmiar.
+ Kliknij na zakładkę Kostiumy i zaimportuj 4 dodatkowe kostiumy. Wybierz cokolwiek Ci się podoba!

+ Wyświetlmy teraz jakiś przypadkowy obrazek. Stwórz poniższy skrypt:

    ```blocks
        kiedy kliknięto zieloną FLAGĘ
        powtórz (losuj od (1) do (5)) razy
            następny kostium
    ```

## Przetestuj swój projekt {.flag}
__Kliknij zieloną flagę.__

Czy duszek ma inny kostium?

__Kliknij flagę jeszcze kilka razy__

Czy duszek ma inny kostium za każdym razem? Czasem ten sam kostium może pojawić się 2 razy z rzędu. Ale nie przejmuj się, to nie jest problem. Prawdopodobnie zauważyliście, że duszek miga za każdym razem jak zmienia kostium. Zaraz naprawimy ten problem.

## Zapisz swój projekt. {.save}

# Krok 2: Zniekształcamy obrazki {.activity}

__Zniekształćmy teraz obrazek, kiedy pojawi się na tablicy po raz pierwszy, a w miarę upływu czasu niech staje się on coraz wyraźniejszy__.

Użyjemy zmiennej z liczbą punktów, aby kontrolować jak bardzo obrazek jest zniekształcony. Jeżeli liczba punktów jest duża, obrazek będzie bardzo zniekształcony.
W miarę jak liczba punktów będzie się zmniejszać z czasem, obrazek będzie coraz wyraźniejszy. Liczba punktów będzie również działać jak zegar. 

## Zadania do wykonania {.check}

+ Kliknij paletę Dane i stwórz zmienną o nazwie 'Punkty'
+ Zmień skrypt, aby wyglądał tak jak ten poniżej:

    ```blocks
        kiedy kliknięto zieloną FLAGĘ
        ukryj
        powtórz (losuj od (1) do (5)) razy
            następny kostium
        koniec
        ustaw [Punkty v] na (110)
        powtarzaj aż ((Punkty) = (0))
            zmień [Punkty v] o (-10)
            ustaw efekt [pikselizacja v] na (Punkty)
            ustaw efekt [kolor v] na (Punkty)
            pokaż
            czekaj (1) s
        koniec
    ```

Nie zapomnij dodać bloku 'ukryj' {.blockpurple} na początku skryptu, `ustawić Punkty na 110` {.blockorange} oraz wszystkiego poniżej.

## Przetestuj swój projekt {.flag}

__Kliknij zieloną flagę.__

+ Czy na tablicy pojawia się przypadkowy, zniekształcony obrazek?
+ Czy obrazek staje się coraz bardziej wyraźny w miarę upływu czasu?
+ Czy liczba punktów zmniejsza się kiedy obrazek staje się coraz bardziej wyraźny?
+ Czy zniekształcenie znika całkowicie, kiedy liczba punktów spadnie do 0?
+ Czy na tablicy pojawia się inny obrazek po każdym wciśnięciu flagi?

## Zapisz swój projekt. {.save}

## Rzeczy do spróbowania {.try .activity}

+ __Spróbuj zmienić liczbę punktów na początku gry i wartość o jaką liczba punktów się zmniejsza w pętli.__ W jaki sposób wpływa to na wygląd obrazka? Czy teraz jest trudniej czy łatwiej odgadnąć co to jest?

+ __Wypróbuj inne efekty graficzne z rozwijanej listy__. W jaki sposób wpływają one na poziom trudności gry?

# Krok 3: Pozwól graczowi zgadnąć co to za obrazek {.activity}

Póki co, nasz przypadkowy obrazek powoli pojawia się na tablicy, a liczba punktów maleje w miarę upływu czasu. Ale jak mamy tę grę wygrać? Najpierw dodamy kilka dodatkowych duszków pod tablicą, które możesz kliknąć. Jeżeli klikniesz odpowiednią miniaturkę, wygrasz grę. Jeżeli klikniesz na zły obrazek, ten duszek zniknie i musisz spróbować zgadnąć jeszcze raz.

Najpierw musimy wiedzieć, która odpowiedź jest poprawna.

+ Stwórz nową zmienną 'dla każdego duszka' i nazwij ją __odpowiedź__.
+ Zmień poprzedni skrypt i ustaw poprawną odpowiedź. Dodaj blok `ustaw [odpowiedź] na kostium #` {.blockorange} zaraz za pierwszą pętlą 'powtórz':

    ```blocks
        kiedy kliknięto zieloną FLAGĘ
        ukryj
        powtórz (losuj od (1) do (5)) razy
            następny kostium
        koniec
        ustaw [odpowiedź v] na (kostium #)
        ustaw [Punkty v] na (110)
        powtarzaj aż ((Punkty) = (0))
            zmień [Punkty v] o (-10)
            ustaw efekt [pikselizacja v] na (Punkty)
            ustaw efekt [kolor v] na (Punkty)
            pokaż
            czekaj (1) s
        koniec
    ```

__Teraz musimy dodać duszki, które gracz będzie mógł kliknąć.__

+ Skopiuj głównego duszka (użyj opcji duplikuj) i umieść go pod tablicą po lewej stronie.
+ Zmień nazwę tego duszka na __odpowiedź1__. (Będzie nam prościej odwoływać się do konkretnych duszków w następnych krokach)
+ Usuń skrypt z duszka __odpowiedź1__ oraz wszystkie jego kostiumy oprócz pierwszego.
+ Powtórz trzy powyższe polecenia, tylko tym razem nazwij duszka __odpowiedź2__ i usuń wszystkie kostiumy oprócz drugiego.
+ W podobny sposób stwórz duszki __odpowiedź3__, __odpowiedź4__ i __odpowiedź5__.

Powinniśmy teraz mieć pięć duszków w rzędzie pod tablicą, każdy z innym kostiumem, który może być wyświetlony na głównym duszku na tablicy. __Upewnij się, że duszki 'odpowiedzi' nie posiadają żadnych skryptów__.

Teraz zmienimy sposób, w jaki duszki będą reagować na kliknięcia myszką. Dalsze akcje będą zależeć od tego, czy odpowiedź jest poprawna.

+ Dodaj poniższy skrypt do duszka 'odpowiedź1':
    ```blocks
        kiedy duszek kliknięty
        jeżeli ((odpowiedź) = (1)) to
            nadaj [wygrana v]
        w przeciwnym razie
            ukryj
    ```

+ Przeciągnij ten skrypt na pozostałe duszki odpowiedzi. __Dla każdego duszka, zmień 1 na 2, 3, itd.__
+ Teraz musimy dodać coś, co będzie reagować na naszą wiadomość 'wygrana'. Kliknij na głównego duszka, tego na tablicy i dodaj do niego ten dodatkowy skrypt:

    ```blocks
        kiedy otrzymam [wygrana v]
        powiedz (połącz [Gratulacje! Twoje punkty: ] i (Punkty))
    ```

## Przetestuj swój projekt {.flag}

__Kliknij zieloną flagę.__

+ Podczas testowania gry warto włączyć podgląd na zmienną __odpowiedź__, aby widzieć poprawną odpowiedź. Na palecie Dane kliknij pole obok zmiennej __odpowiedź__, a pojawi się ona na scenie, w lewym górnym rogu.
+ Co się dzieje po kliknięciu na __poprawną__ odpowiedź?
+ Co się dzieje po kliknięciu na __niepoprawną__ odpowiedź?
+ Co się dzieje z niepoprawną odpowiedzią __po rozpoczęciu nowej gry?__

Podczas testów zauważysz pewnie dwa problemy. Po pierwsze, duszki z niepoprawnymi odpowiedziami nie wracają na ekran po rozpoczęciu nowej gry. Po drugie, liczba punktów nie zatrzymuje się przy kliknięciu na poprawną odpowiedź.

+ Aby naprawić pierwszy problem, dodaj poniższy skrypt do wszystkich duszków odpowiedzi:
    ```blocks
        kiedy kliknięto zieloną FLAGĘ
        pokaż
    ```

Aby naprawić drugi problem, trzeba zatrzymać pętlę 'powtórz' na duszku odpowiedzi po kliknięciu poprawnej odpowiedzi. Wymaga to nowej zmiennej. Ustaw ją na __0__ po rozpoczęciu gry, a potem na __1__ po wygraniu gry.

+ Stwórz nową zmienną i nazwij ją 'wygrano?'
+ Zmień istniejące skrypty, aby wyglądały tak jak poniżej:

    ```blocks
        kiedy kliknięto zieloną FLAGĘ
        ukryj
        powtórz (losuj od (1) do (5)) razy
            następny kostium
        koniec
        ustaw [odpowiedź v] na (kostium #)
        ustaw [Punkty v] na (110)
        ustaw [wygrano? v] na (0)
        powtarzaj aż (((Punkty) = (0)) lub ((wygrano?) = (1))
            zmień [Punkty v] o (-10)
            ustaw efekt [pikselizacja v] na (Punkty)
            ustaw efekt [kolor v] na (Punkty)
            pokaż
            czekaj (1) s
        koniec
    
        kiedy otrzymam [wygrana v]
        ustaw [wygrano? v] na (1)
        wyczyść efekty graficzne
        powiedz (połącz [Gratulacje! Twoje punkty: ] i (Punkty))
    ```

## Zapisz swój projekt. {.save}

__Brawo! Podstawowa wersja gry jest już gotowa!__

Jest jeszcze kilka rzeczy, które można zmienić, aby ulepszyć grę. Spróbuj zrobić poniższe wyzwania!

## Wyzwanie 1: Spraw, aby gra była trudniejsza albo łatwiejsza {.challenge}

Zmień poziom trudności gry.

* Zobacz, co się stanie, gdy zmienisz szybkość z jaką obrazek staje się wyraźniejszy lub z jaką zmniejsza się liczba punktów.
* Spróbuj zmienić rodzaj zniekształceń obrazka.
* Użyj innych obrazków. Sprawdź, czy gra jest trudniejsza czy łatwiejsza, gdy obrazki są podobne do siebie. A jak się gra, gdy obrazki znacząco się od siebie różnią? Nie zapomnij zmienić kostiumów na duszkach odpowiedzi.

## Zapisz swój projekt. {.save}

## Wyzwanie 2: Zniekształć obrazek w inny sposób w każdej grze {.challenge}

Teraz, za każdym razem, gdy zaczynasz grę, obrazki są zniekształcone w ten sam sposób. W drugim kroku próbowaliśmy kombinacji różnych zniekształceń, które działały równie dobrze jak zmiana koloru i pikselizacja.

Spróbuj użyć innych kombinacji zniekształceń, które działałyby równie dobrze.

Zmień grę w taki sposób, że za każdym razem obrazki zniekształcane są w inny sposób.

__Podpowiedź:__ Stwórz nową zmienną i nazwij ją 'zniekształcenie'. Przypisz jej przypadkową wartość zaraz na początku gry. Użyj bloku jeżeli w pętli 'powtarzaj aż', aby użyć odpowiedniego zniekształcenia.

## Zapisz swój projekt. {.save}

## Wyzwanie 3: Spraw, aby w grze było kilka rund {.challenge}

Obecnie każda gra jest niezależna. Zmień grę tak, aby można było zagrać w nią kilka razy. Na przykład, niech gracz w ciągu jednej gry ma 3 rundy - niech spróbuje odgadnąć 3 obrazki i zdobyć maksymalnie 300 punktów.

__Podpowiedź:__ Będziesz potrzebować dodatkowej zmiennej, aby wiedzieć, ile rund ma mieć każda gra. Będziesz również potrzebować odpowiedniej pętli, aby gra odbywała się w rundach.

__Podpowiedź:__ Pamiętaj, aby duszki, które zniknęły po złej odpowiedzi, pojawiły się z powrotem na ekranie na początku każdej rundy. Aby to zrobić, spróbuj nadać jakąś wiadomość.

## Zapisz swój projekt. {.save}

## Wyzwanie 4: Spraw, aby każda następna runda była trudniejsza {.challenge}

Spraw, aby gra była coraz trudniejsza z rundy na rundę.

Czy w każdej rundzie punkty powinny być przyznawane w ten sam sposób? Może gracz powinien zdobywać więcej punktów w póżniejszych rundach, jeżeli szybciej odgadnie obrazek?

__Podpowiedź:__ Skąd będziemy wiedzieć, w której jesteśmy rundzie gry? W jaki sposób pomoże nam to zwiększyć trudność gry i przyznawać więcej punktów?

## Zapisz swój projekt. {.save}

## Wyzwanie 5: Graj tak długo, aż się pomylisz {.challenge}

Zamiast grać w określoną liczbę rund, spróbujmy zmienić grę tak, aby gracz mógł w nią grać dopóki się nie pomyli. Taki system gry będzie miał tylko sens, jeżeli gra będzie się robić coraz trudniejsza z każdą następną rundą.

## Zapisz swój projekt. {.save}

## Wyzwanie 6: Spraw, aby gra była trudniejsza albo łatwiejsza w zależności od tego jak dobrze gracz zgaduje {.challenge}

Spróbujmy dostosować trudność gry do umiejętności gracza, zamiast zwiększać trudność gry z każdą rundą. Jeżeli gracz odgadnie obrazek szybko, spraw, aby gra była trudniejsza w następnej rundzie. Ale jeżeli gracz się pomyli, albo potrzebuje więcej czasu, aby odgadnąć obrazek, niech następna runda będzie troszkę łatwiejsza.

Ten pomysł będzie miał sens tylko wtedy, kiedy nie będziemy sumować ilości punktów w ciągu całej gry.

## Zapisz swój projekt. {.save}

## Wyzwanie 7: Zapamiętaj najlepszy wynik {.challenge}

Zapamiętaj najlepszy wynik. Jeżeli ktoś będzie lepszy w kolejnej grze, zapytaj gracza o jego imię i zapisz nowy najlepszy wynik. Upewnij się, że najlepszy wynik i imię najlepszego gracza są wyświetlone na ekranie.

## Zapisz swój projekt. {.save}

## Wyzwanie 8: Za niepoprawną odpowiedź odejmij punkty {.challenge}

Póki co, gracz nie jest karany za niepoprawne odpowiedzi, więc teoretycznie może spróbować kliknąć na wszystkie odpowiedzi tak szybko jak się da, aż w końcu trafi na dobrą odpowiedź. Zmieńmy grę, aby za każdą niepoprawną odpowiedź gracz tracił punkty.

Jak myślisz, czy gra teraz jest lepsza?

## Zapisz swój projekt. {.save}

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.
