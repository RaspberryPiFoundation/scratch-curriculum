Poziom 3

#Co to jest

__Wstęp:__
Na tablicy jest pokazany jakiś obrazek, ale zniekształcony. Musisz zgadnąć co to jest klikając na odpowiednią odpowiedź poniżej. Im szybciej zgadniesz, tym więcej punktów otrzymasz!

##KROK 1: Wyświetl różne obrazki na tablicy

Chcemy pokazać na tablicy kilka różnych obrazków.

1. Stwórz nowy projekt Scratch i usuń duszka kota.
2. Kliknij na Scenę, a następnie na zakładkę Tła. Zaimportuj tło 'indoors/chalkboard'.
3. Zaimportuj nowego duszka i dodaj do niego kostium. Wybierz taki kostium, który Ci się podoba. Może znajdziesz coś ciekawego w katalogu 'things'.
4. Umieść tego duszka na środku tablicy. Jeżeli trzeba, odpowiednio zwiększ lub zmniejsz jego rozmiar.
5. Kliknij na zakładkę Kostiumy i zaimportuj 4 dodatkowe kostiumy. Wybierz cokolwiek Ci się podoba!

Wyświetlmy teraz jakiś przypadkowy obrazek.

6. Stwórz poniższy skrypt:

```scratch

	kiedy kliknięto FLAGĘ
	powtórz losuj liczbę pomiędzy 1 a 5 razy
	    następny kostium
	(koniec powtórz)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy duszek ma inny kostium?

__Kliknij flagę jeszcze kilka razy__
Czy duszek ma inny kostium za każdym razem? Czasem, ten sam kostium może pojawić się 2 razy z rzędu. Ale nie przejmuj się, to nie jest problem. Prawdopodobnie zauważyliście, że duszek miga za każdym razem jak zmienia kostium. Zaraz naprawimy ten problem.

Zapisz swój projekt.

##KROK 2: Zniekształć obrazki

__Zniekształćmy teraz obrazek, kiedy pojawi się na tablicy po raz pierwszy, a w miarę upływu czasu niech staje się on coraz bardziej wyraźny__.

Użyjemy zmiennej z ilością punktów, aby kontrolować jak bardzo obrazek jest zniekształcony. Jeżeli ilośc punktów jest duża, obrazek będzie bardzo zniekształcony.
W miarę upływu czasu, jak ilośc punktów będzie się zmniejszać, obrazek będzie coraz wyraźniejszy. Ilość punktów będzie również działać jak zegar. Całkiem jak na karcie __Timer__ (Zegar).

1. Kliknij paletę Zmienne, i stwórz zmienną o nazwie 'Punkty'

2. Zmień skrypt aby wyglądał tak jak ten poniżej:

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	powtórz losuj liczbę pomiędzy 1 a 5 razy
	    następny kostium
	(koniec powtórz)
	ustaw Punkty na 110
	powtarzaj aż Punkty = 0
		zmień Punkty o -10
		ustaw efekt pikselizacja na Punkty
		ustaw efekt kolor na Punkty
		pokaż
		czekaj 1 s
	(koniec powtórz)
```

Nie zapomnij dodać bloku ukryj na początku skryptu, ustawić Punkty na 110 oraz wszystkiego poniżej.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy na tablicy pojawia się przypadkowy, zniekształcony obrazek?

Czy obrazek staje się coraz bardziej wyraźny w miarę upływu czasu?

Czy ilość punktów zmniejsza się jak obrazek staje się coraz bardziej wyraźny?

Czy zniekształcenie znika całkowicie kiedy ilość punktów osiąga 0?

Czy ciągle na tablicy pojawia się inny obrazek za każdym razem jak klikniesz zieloną flagę?


Zapisz swój projekt.

##Rzeczy do spróbowania

__Spróbuj zmienić ilość punktów na początku gry i wartość o jaką ilość punktów się zmniejsza w pętli__. W jaki sposób wpływa to na wygląd obrazka? Czy teraz jest trudniej czy łatwiej odgadnąć jaki to jest obrazek?

__Wypróbuj inne efekty graficzne z rozwijanej listy__. W jaki sposób wpływają one na poziom trudności gry?

##KROK 3: Pozwól graczowi zgadnąć jaki to jest obrazek

Póki co, nasz przypadkowy obrazek powoli pojawia się na tablicy, a ilość punktów maleje w miarę upływu czasu. Ale jak mamy tę grę wygrać? Najpierw dodamy kilka dodatkowych duszków pod tablicą, które możesz kliknąć. Jeżeli klikniesz poprawny obrazek, wygrasz grę. Jeżeli klikniesz na nieodpowiedni obrazek, ten duszek zniknie i musisz spróbować zgadnąć jeszcze raz.

Najpierw, musimy wiedzieć, która odpowiedź jest poprawna.

1. Stwórz nową zmienna 'dla każdego duszka' i nazwij ją __odpowiedź__.
2. Zmień poprzedni skrypt i ustaw poprawną odpowedź. Dodaj blok 'ustaw odpowiedź na kostium #' zaraz za pierwszą pętlą 'powtórz':

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	powtórz losuj liczbę pomiędzy 1 a 5 razy
	    następny kostium
	(koniec powtórz)
    ustaw odpowiedź na kostium #
    ustaw Punkty na 110
	powtarzaj aż Punkty = 0
		zmień Punkty o -10
		ustaw efekt pikselizacja na Punkty
		ustaw efekt kolor na Punkty
		pokaż
		czekaj 1 s
	(koniec powtórz)
```

__Teraz musimy dodać duszki, które gracz będzie mógł kliknąć.__

3. Skopiuj głównego duszka (użyj opcji duplikuj) i umieść go pod tablicą po lewej stronie.
4. Zmień nazwę tego duszka na __odpowiedź1__. (Będzie nam prościej odwoływać się do konkretnych duszków w następnych krokach)
5. Usuń skrypt z duszka __odpowiedź1__ oeraz wszystkie jego kostiumy oprócz pierwszego.
6. Powtórz trzy ostatnie polecenia, tylko tym razem nazwij duszka __odpowiedź2__ i usuń wszystkie kostiumy oprócz drugiego.
7. W podobny sposób stwórz duszki __odpowiedź3__, __odpowiedź4__ i __odpowiedź5__.

Powinniśmy teraz mieć 5 duszków w rzędzie pod tablicą, każdy z innym kostiumem, który może być wyświetlony na głównym duszku na tablicy. __Upewnij się, że żaden z duszków 'odpowiedzi' nie posiada żadnego skryptu__.

Teraz zmienimy sposób w jaki duszki będą reagować na kliknięcia myszką. W zależności od tego czy odpowiedź jest poprawna czy nie, wykonamy inną akcję.

8. Dodaj poniższy skrypt do duszka 'odpowiedź1':

```scratch

	kiedy kliknięto odpowiedź1
	jeżeli odpowiedź=1
		nadaj wygrana
	w przeciwnym przypadku
		ukryj
	(koniec jeżeli)
```

9. Przeciągnij ten skrypt na pozostały duszki odpowiedzi. __Na każdym z tych duszków, zmień 1 na 2, 3, itd.__
10. Teraz musimy dodać coś, co będzie reagować na naszą wiadomość 'wygrana'. Kliknij na głównego duszka, tego na tablicy i dodaj do niego ten dodatkowy skrypt:

```scratch

	kiedy otrzymam wygrana
	powiedz połącz Gratulacje! Zdobyłeś Punkty
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Kiedy będziecie testować grę, warto włączyć podgląd na zmienną __odpowiedź__, żeby zobaczyć, która odpowiedź jest poprawna. Na palecie Zmienne kliknijcie pole obok zmiennej __odpowiedź__, a pojawi się ona na scenie, w lewym górnym rogu.

Co się dzieje, kiedy klikniecie na __poprawną__ odpowiedź?

Co się dzieje, kiedy klikniecie na __niepoprawną__ odpowiedź?

Co się dzieje z niepoprawną odpowiedzią, kiedy __zaczynacie nową grę?__

Podczas naszych testów powinniście znaleźć 2 problemy. Po pierwsze, duszki z niepoprawnymi odpowiedziami nie pojawiają się z powrotem na ekranie, kiedy zaczynamy nową grę. Po drugie, ilość punktów nie zatrzymuje się w momencie gdy klikniemy poprawną odpowiedź.

11. Aby naprawić pierwszy problem, dodaj poniższy skrypt do wszystkich duszków odpowiedzi:


```scratch

	kiedy kliknięto FLAGĘ
	pokaż
```

Aby naprawić drugi problem, musimy zatrzymać pętlę 'powtórz' na duszku odpowiedzi, jak gracz kliknie poprawną odpowiedź. Stworzymy do tego celu nową zmienną. Ustawimy ją na __0__ kiedy rozpocznie się nowa gra, a potem ustawimy ją na __1__, kiedy grę wygramy.
To fix the second problem, we need to stop the __question sprite__’s repeat until loop when the player clicks on the right answer. We’ll use a new variable to do that. We’ll set it to __zero__ when the game starts and set it to __one__ when the game is won. Pętla 'powtórz' musi się zatrzymać kiedy ilość Punktów osiągnie __0__ albo kiedy __flaga wygrana__ jest ustawiona na __1__.

12. Stwórz nową zmienną i nazwij ją wygrano?
13. Zmień istnięjące skrypty, aby wyglądały tak jak poniżej:

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	powtórz losuj liczbę pomiędzy 1 a 5 razy
	    następny kostium
	(koniec powtórz)
    ustaw odpowiedź na kostium #
    ustaw Punkty na 110
    ustaw wygrano? na 0
	powtarzaj aż Punkty = 0 lub wygrano? = 1
		zmień Punkty o -10
		ustaw efekt pikselizacja na Punkty
		ustaw efekt kolor na Punkty
		pokaż
		czekaj 1 s
	(koniec powtórz)

	kiedy otrzymam wygrana
	ustaw wygrano? na 1
	wyczyść efekty graficzne
	powiedz połącz Gratulacje! Zdobyłeś Punkty
```

Zapisz swój projekt.

__Brawo! Podstawowa wersja gry jest już gotowa!__

Ale jest kilka rzeczy, które możesz zmienić, aby twoja gra była jeszcze lepsza. Zobacz czy uda się zrobić poniższe wyzwania!

##Challenge 1: Make the game harder or easier

Change how difficult the game is.

* Try changing how fast the picture is revealed and how fast the score goes down.
* Try changing the distortions on the picture.
* Try changing the pictures being guessed, to make them either more similar or more different. If you do this, don’t forget to change the answer sprite’s costume.

Save your project

##Challenge 2: Distort the picture differently in each game

At the moment, each play of the game uses the same distortion. In Step 2, you might have tried some different distortions that work at least as well as the colour + pixelation we used.

Find some different distortions that work well.

Change the game so that each game uses a different distortion in the repeat until loop.

__Hint:__ Try creating a new variable, called distortion to use. Set it to a random value at the start of the game. Use if blocks in the body of the repeat until loop to apply the correct distortion for this game.

Save your project

##Challenge 3: Make a game have a few rounds

At the moment, each game is independent. Change it so that the game proceeds in several rounds. For instance, have one game take three rounds, so the player has to guess three pictures and can score up to 300 points.

__Hint:__ You’ll need an extra variable to store the grand total across all the rounds. You’ll also need a loop to go through the different rounds.

__Hint:__ You’ll also have to make the wrong guesses reappear at the start of each round. Perhaps you could use a broadcast message to do that?

Save your project

##Challenge 4: Make later rounds more difficult

As you go through different rounds, make the game harder each time.

Does each round need to score the same? Should you get more points for guessing quickly in the later, more difficult rounds?

__Hint:__ How will you know which round you’re in? How can you use that to change the difficulty and the score?

Save your project

##Challenge 5: Keep playing until the player gets it wrong

Instead of using a fixed number of rounds, keep playing the game until the player doesn’t get a picture right. This probably only works if the game gets harder in later rounds.

Save your project

##Challenge 6: Make the game harder or easier depending on how well the player does

Rather than always making the game harder, make the game adjust the difficulty depending on the skill of the player. If they get the right picture quickly, make the next game a bit harder. If they don’t get the right picture, or only get it late, make the next game a bit easier.

This idea only really works if you don’t add up someone’s score over several rounds.

Save your project

##Challenge 7: Keep track of the highest score

Keep track of the highest score. If someone manages to beat it, ask for their name and update the highest score. Make sure the highest score, and the name of the person who scored it, are displayed.

Save your project


##Challenge 8: Make wrong guesses expensive

At the moment, there’s no penalty to just clicking on all the answer sprites as quickly as you can. Change the game so that the score goes down a bit every time you make an incorrect guess.

Does this make the game better?

Save your project


__Well done you’ve finished, now you can enjoy the game!__
Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
