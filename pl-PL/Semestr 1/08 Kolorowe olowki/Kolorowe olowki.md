Poziom 3

#Kolorowe ołówki

__Wstęp:__
Podczas tego projektu stworzymy podstawowe narzędzia do rysowania. Będzie można rysować po ekranie kursorem myszy, zmieniać kolor linii, czyścić ekran czy robić pieczątki!

##KROK 1: Rysowanie kursorem myszy

Zaczniemy od stworzenia ołówka, który rysuje, gdy przeciąga się go po scenie.

1. Rozpocznij nowy projekt w Scratchu. Skasuj duszka kota klikając na nim prawym przyciskiem myszy i wybierając Usuń.
2. Kliknij na Scenę i przejdź do karty Tła. Wybierz tablicę z katalogu Zasoby.
3. Stwórz nowego duszka o nazwie __ołówek__, wybierając __zielony-ołówek__ z katalogu Zasoby.
4. Przejdź na kartę z kostiumami i kliknij na edycję kostiumu. W edytorze obrazów zmień centrum kostiumu na rysik ołówka. Aby to zrobić, kliknij __Ustaw środek kostiumu__ i przesuń punkt przecięcia linii na ekranie, aby był na końcu rysika.
5. Spraw, aby ołówek podążał za kursorem myszy korzystając z bloków __zawsze__ oraz __idź do__. 

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		idź do wskaźnik myszy
	(koniec zawsze)
```

__Teraz chcemy używać tego duszka jak prawdziwego ołówka.__ Jeżeli zajrzysz do panelu Pisak, znajdziesz tam bloki związane z rysowaniem. Na chwilę obecną interesują nas bloki __przyłóż pisak__ i __podnieś pisak__.

6. Chcemy kontrolować ołówek przyciskiem myszy: jeżeli przycisk jest wciśnięty, ołówek dotyka tablicy, a kiedy nie jest wciśnięty, ołówek nie dotyka tablicy. Możemy to kontrolować korzystając z bloku __jeżeli... w przeciwnym przypadku__.

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		idź do wskaźnik myszy
		jeżeli wciśnięty klawisz myszy?
			przyłóż pisak
		w przeciwnym przypadku
			podnieś pisak
		(koniec jeżeli)
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Czy ołówek podąża za kursorem myszy? Co się dzieje, kiedy wciśniesz przycisk myszy i ją przesuniesz? Nie przejmuj się na razie kolorem myszy.

7. Prędzej czy później ekran zapełni się rysunkami. Użyj bloku __wyczyść__ do czyszczenia ekranu.

```scratch

	kiedy kliknięto Flagę
	wyczyść
	zawsze
		idź do wskaźnik myszy
		jeżeli wciśnięty klawisz myszy?
			przyłóż pisak
		w przeciwnym przypadku
			podnieś pisak
		(koniec jeżeli)
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy rysunek znika po wciśnięciu flagi?

Zapisz swój projekt.

##KROK 2: Czyszczenie ekranu

Zamiast uruchamiać cały projekt ponownie, aby wyczyścić ekran, dodajmy przycisk czyszczący. Możemy do tego także wykorzystać blok __wyczyść__.

1. Stwórz nowego duszka korzytając z kostiumu __wyczyść przycisk__ z katalogu Zaosby.
2. Zmień nazwę duszka na __wyczyść__.
3. Przesuń duszka do dolnego lewego rogu sceny.
4. Dodaj poniższy skrypt:

```scratch
	
	kiedy kliknięto wyczyść
	wyczyść
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy przycisk czyści ekran z rysunków?

Zapisz swój projekt.

##KROK 3: Zmienianie kolorów

Do tej pory mogliśmy rysować tylko niebieskie linie. Pora zacząć zmieniać kolory! Dodamy kilka duszków na dole ekranu, które wyglądają jak kolorowe przyciski i klikając na nie, będziemy zmieniać kolor linii oraz duszka ołówka. 

1. Dodaj nowego duszka i nazwij go __czerwony__. Użyj kostiumu __czerwony-kolor__ z katalogu Zasoby.
2. Ustaw go na dole ekranu, niedaleko przycisku __wyczyść__.
3. Po wciśnięciu, duszek czerwony powinien nadawać wiadomość __czerwony__.


```scratch
	
	kiedy kliknięto czerwony
	nadaj czerwony
```

__Tak, to wszystko co ma robić ten duszek. Całą trudną robotą zajmuje się ołówek.__

Przejdź do duszka ołówka i zaimportuj kostium __czerwony-olowek__ z katalogu Zasoby. Ustaw centrum kostiumu na końcu rysika tak jak dla oryginalnego kostiumu.

4. Dodaj nowy skrypt do ołówka. Kiedy ołówek otrzyma wiadomość __czerwony__, powinien zmienić swój kostium oraz zmienić kolor linii. 

__Wskazówka:__ jeżeli klikniesz na kolorowy kwadrat bloku __ustaw kolor pisaka na__, kursor zmieni się w pipetę – możesz nią kliknąć na czerwonym duszku, aby upewnić się, że używasz tego samego odcienia czerwonego.

```scratch
	
	kiedy otrzymam czerwony
	zmień kostium na czerwony-olowek
	ustaw kolor pisaka na (czerwony)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Narysuj linię, a następnie kliknij na przycisk zmiany koloru na czerwony i narysuj coś jeszcze. Czy ołówek zmienił kostium? Czy rysuje teraz na czerwono? Czy rysuje końcem rysika?

Zapisz swój projekt

5. Powtórz powyższe kroki dodając duszki wyboru niebieskiego, żółtego i zielonego koloru.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wszystkie przyciski wyboru koloru działają? Czy wszystkie zmieniają kostium na odpowiedni kolor? Czy po zmianie wszystkie linie są w odpowiednim kolorze? Czy wszystkie kostiumy rysują czubkiem rysika?

Zapisz swój projekt

##KROK 4: Rysowanie tylko wewnątrz danego obszaru

Obecnie możemy rysować po całej scenie, nie tylko po tablicy. Trzeba to naprawić. Chcemy, aby można było rysować tylko po tablicy, trzeba więc będzie pilnować, aby ołówek nie wyszedł poza dozwolony obszar (tablicę).

Pamiętaj, że Scratch określa punkty korzystając ze współrzędnych na osiach x i y. Tablica, po której chcemy rysować, znajduje się pomiędzy punktem -230 a 230 na osi x i pomiędzy -120 a 170 na osi y. Możemy użyć te wartości w bloku __jeżeli__, aby sprawdzać, czy kursor myszy znajduje się w tym obszarze, zanim przesuniemy ołówek w jego kierunku.

Aby to zrobić, owiń istniejący blok __idź do... jeżeli__  w kolejny blok __jeżeli__, który będzie sprawdzał położenie kursora myszy. Współrzędne kursora na osi x powinny być większe -230 i mniejsze niż 230, a współrzędne na osi y powinny być większe niż -120 i mniejsze od 170.

__Uwaga__. Aby to zrobić, potrzebujesz użyć kilku bloków z operatorem __i__: jeden dla obu warunków dla współrzędnych na osi x, jeden dla obu warunków dla współrzędnych na osi y oraz jeden do połączenia wszystkich warunków ze sobą.

```scratch
	wyczyść
	zawsze
		jeżeli x myszy > -230 i x myszy < 230 i y myszy > -120 i y myszy < 170
		idź do wskaźnik myszy
```

Skoro nie możemy rysować poza wyznaczonym obszarem, byłoby dobrze chować ołówek, kiedy wyjdziemy poza tablicę. Aby to zrobić, zamień blok __jeżeli__ na blok __jeżeli w przeciwnym przypadku__. Zostaw warunek, który masz w __jeżeli__ i __pokaż__ ołówek, kiedy to prawda i chowaj go, kiedy warunek nie jest spełniony.

```scratch

	kiedy kliknięto FLAGĘ
	podnieś pisak
	wyczyść
	zawsze
		jeżeli x myszy > -230 i x myszy < 230 i y myszy > -120 i y myszy < 170
			idź do wskaźnik myszy
			pokaż
			jeżeli wciśnięty klawisz myszy?
				przyłóż pisak
				w przeciwnym przypadku
				podnieś pisak
			(koniec jeżeli)
		w przeciwnym przypadku
			ukryj
		(koniec jeżeli)
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy możesz ciągle rysować po tablicy? Możesz rysować poza tym obszarem? Co się dzieje, kiedy wyjdziesz poza obszar, po którym można rysować, a potem do niego wrócisz?

Zapisz swój projekt.

##KROK 5: Gumka

__Super, że możemy już rysować, ale przydałoby się dodać gumkę do poprawiania drobnych błędów.__ Możemy to zrobić dodając nowy ołówek, który rysuje na szaro (czyli w tym samym kolorze, co tło).

Dodaj nowego duszka i wybierz dla niego kostium __gumka__ z katalogu Zasoby. Zmniejsz go, aby zmieścił się na dole ekranu i pasował do pozostałych przycisków. Nowy przycisk powinien działać tak samo, jak poprzednie i nadawać informacje, że jest gumką.

Duszek ołówek powinien reagować na wiadomość gumki i zmieniać kolor na szary (pamiętaj, że możesz użyć pipetę, aby wybrać odpowiedni kolor z tła). Duszek potrzebuje też nowy kostium – użyj tej samej gumki, co do przycisku wcześniej. __Pamiętaj, aby ustawić środek duszka na jego brzegu__.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy gumka działa? Czy działa przy samych brzegach ekranu? Możesz przełączać się między gumką a ołówkami?

Zapisz swój projekt.

##STEP 6: Stamps

The next thing to add is a stamp tool, to stamp small pictures on the drawing.
Activity Checklist

1. Add a new sprite, using whichever image or costume you want. Shrink the sprite down and place it at the bottom of the screen alongside the other tools. When this sprite is clicked, it should __broadcast stamp__
2. Add a new costume for this pencil sprite, the same as the one you chose for the __stamp__ button.
3. Select the pencil sprite and create a new variable __pencil mode__ for this sprite only. We’ll use this variable to keep track of whether or not we are drawing or stamping.
4. Add a new script to respond to the stamp message. It needs to set the costume to the stamp and set the __pencil mode__ variable to __false__.
5. Change the other scripts that respond to tool-selection messages (red, green, blue, and eraser) so that they each set the __pencil mode__ to __true__.
6. Finally, lets check this variable __when the mouse button is down__ to see if we should be drawing or stamping. If pencil mode = true we should use the existing __pen down__, if not we should stamp instead. 

##Test Your Project
__Click on the green flag.__

Does the stamp tool work correctly?

What happens when you switch back to one of the normal pencil tools?

SAVE YOUR PROJECT

__Well done, you have completed the basic steps for this project.
Try these challenges!__

##Challenge 1: Rainbow pencil

Let’s add a special pencil that paints in rainbow colours. It’s something that you can’t do with ordinary pens and pencils, so it’s nice to show off how drawing on a computer allows you do to different things. The secret to making it work is the change pen colour by block.

First, add the rainbow tool selection sprite and the rainbow tool costume to the pencil sprite:

1. Create a new tool selection sprite and place it at the bottom of the stage, alongside all the other pencil colour sprites. Use the resources/rainbow-selector costume and have it broadcast rainbow when clicked.
2. Add the resources/rainbow-pencil costume to the pencil sprite.

You need to build a script that will change the pen colour many times a second to give the rainbow effect (I found that changing it by 5 every 0.05 seconds works well, but you should try out different values). The timer Scratch card shows how you can make something change every so often. Use a change pen colour by 5 block instead of a change timer by -1 block inside the loop.

You also need to control that loop so that it only changes the pen colour when you’ve selected the rainbow pencil, otherwise all the pencils will have a rainbow effect! You can do this in a very similar way to how the pencil sprite changes between pencil and stamp modes. You need to create a variable called rainbowChange that has the value true when you want the rainbow effect and false otherwise. Every time the pencil responds to a tool-selection message, it should set the value of rainbowChange accordingly.

Use what you learnt from the stamp step above to control the rainbow effect. The scripts that respond to the tool-selection messages will set two variables each: pencilMode and rainbowChange.

##Test Your Project
__Click on the green flag.__

Does the rainbow tool work correctly?

What happens when you switch back to one of the normal pencil tools?

SAVE YOUR PROJECT

##Challenge 2: Keyboard shortcuts

Rather than using the tool-selection sprites at the bottom of the stage, you can use the keyboard to select the different tools.
You can use the when [] key pressed blocks to respond to the keyboard. For each key you want to use, you’ll need another when [] key pressed block, which sends the same message as the respective tool-selection sprite does when its clicked. Add these scripts to the stage.

I used these shortcuts:
* Clear all - a
* Eraser - e
* Red pencil -r 
* Blue pencil - b
* Yellow pencil - y
* Green pencil - g
* Rainbow pencil - w
* Stamp - s

##Test Your Project
__Click on the green flag.__

Do all the tools get selected with the correct keyboard shortcuts? Does each of the tools work correctly when you select it with keyboard? Are the correct tools still selected with the tool-selection sprites on the stage?

SAVE YOUR PROJECT

##Challenge 3: Big and Small
Another feature that most drawing packages have is the ability to change the
size of the pencil. Let’s add that.
There’s one complication, though, which is that sometimes the resizing needs to change the pen size and sometimes it needs to change the pencil sprite’s costume size. It depends on whether you’re using a pencil or a stamp.

Create two new tool-selection sprites, called bigger and smaller. They should have the resources/bigger-selector and resources/smaller-selector costumes and should send the bigger and smaller messages.

The pencil sprite can respond to the messages by changing either the pen size by 1 or the costume size by 10, depending on the value of pencil mode (use an if-else block, similar to how the sprite chooses between putting the pen down or stamping)
Don’t forget the keyboard shortcuts for the bigger and smaller tools. I used the up and down arrows.

SAVE YOUR PROJECT

What you should have noticed is that changing the size of the stamp also changes the size of the pencil on-screen when you change to that tool.
To stop that, you need to set the size to 100% every time you change to a pencil tool. so that the tools look the right size.

To make it even better, have the stamp remember what size it was before you selected the pencil and go back to that size when you select the stamp tool again. The easiest way to do that is to create a new variable called stampSize, that is updated with the current size every time the stamp is resized. When the stamp tool is selected, it can set its size from the contents of this variable.

##Test Your Project
__Click on the green flag.__

Do the size controls work for the pencils?

What happens if you switch to the stamp, change the size and then switch back to a pencil?

SAVE YOUR PROJECT


__Well done you’ve finished, now you can enjoy the game!__


Don’t forget you can share your game with all your friends and family by clicking on __Share__ on the menu bar!
