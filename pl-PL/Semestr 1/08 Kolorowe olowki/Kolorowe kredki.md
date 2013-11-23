Poziom 3

#Kolorowe kredki

__Wstęp:__
Podczas tego projektu stworzymy podstawowe narzędzia do rysowania. Będzie można rysować po ekranie kursorem myszy, zmieniać kolor linii, czyścić ekran czy robić pieczątki!

##KROK 1: Rysowanie kursorem myszy

Zaczniemy od stworzenia kredki, która rysuje, gdy przeciąga się ją po scenie.

1. Rozpocznij nowy projekt w Scratchu. Skasuj duszka kota, klikając na nim prawym przyciskiem myszy i wybierając Usuń.
2. Kliknij na Scenę i przejdź do karty Tła. Wybierz tablicę z katalogu Zasoby.
3. Stwórz nowego duszka o nazwie __kredka__, wybierając __zielona-kredka__ z katalogu Zasoby.
4. Przejdź na kartę z kostiumami i kliknij na edycję kostiumu. W edytorze obrazów zmień centrum kostiumu na rysik kredki. Aby to zrobić, kliknij __Ustaw środek kostiumu__ i przesuń punkt przecięcia linii na ekranie, aby był na końcu rysika.
5. Spraw, aby kredka podążała za kursorem myszy. Skorzystaj z bloków __zawsze__ oraz __idź do__. 

```scratch

	kiedy kliknięto FLAGĘ
	zawsze
		idź do wskaźnik myszy
	(koniec zawsze)
```

__Teraz chcemy używać tego duszka jak prawdziwej kredki.__ Jeżeli zajrzysz do panelu Pisak, znajdziesz tam bloki związane z rysowaniem. Na chwilę obecną interesują nas bloki __przyłóż pisak__ i __podnieś pisak__.

6. Chcemy kontrolować kredkę przyciskiem myszy: jeżeli przycisk jest wciśnięty, kredka dotyka tablicy, a kiedy nie jest wciśnięty, kredka nie dotyka tablicy. Możemy to kontrolować korzystając z bloku __jeżeli... w przeciwnym przypadku__.

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
Czy kredka podąża za kursorem myszy? Co się dzieje, kiedy wciśniesz przycisk myszy i ją przesuniesz? Nie przejmuj się na razie kolorem linii.

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

1. Stwórz nowego duszka korzystając z kostiumu __wyczyść przycisk__ z katalogu Zasoby.
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

Do tej pory mogliśmy rysować tylko niebieskie linie. Pora zacząć zmieniać kolory! Dodamy kilka duszków na dole ekranu, które wyglądają jak kolorowe przyciski i klikając na nie, będziemy zmieniać kolor linii oraz kolor duszka-kredki. 

1. Dodaj nowego duszka i nazwij go __czerwony__. Użyj kostiumu __czerwony-kolor__ z katalogu Zasoby.
2. Ustaw go na dole ekranu, niedaleko przycisku __wyczyść__.
3. Po wciśnięciu, duszek czerwony powinien nadawać wiadomość __czerwony__.


```scratch
	
	kiedy kliknięto czerwony
	nadaj czerwony
```

__Tak, to wszystko co ma robić ten duszek. Całą trudną robotą zajmuje się kredka.__

Przejdź do duszka-kredki i zaimportuj kostium __czerwona kredka__ z katalogu Zasoby. Ustaw centrum kostiumu na końcu rysika tak jak dla oryginalnego kostiumu.

4. Dodaj nowy skrypt do kredki. Kiedy kredka otrzyma wiadomość __czerwony__, powinna zmienić swój kostium oraz zmienić kolor linii. 

__Wskazówka:__ jeżeli klikniesz na kolorowy kwadrat bloku __ustaw kolor pisaka na__, kursor zmieni się w pipetę – możesz nią kliknąć na czerwonym duszku, aby upewnić się, że używasz tego samego odcienia czerwonego.

```scratch
	
	kiedy otrzymam czerwony
	zmień kostium na czerwony-olowek
	ustaw kolor pisaka na (czerwony)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Narysuj linię, a następnie kliknij na przycisk zmiany koloru na czerwony i narysuj coś jeszcze. Czy kredka zmieniła kostium? Czy rysuje teraz na czerwono? Czy rysuje końcem rysika?

Zapisz swój projekt.

5. Powtórz powyższe kroki dodając duszki wyboru niebieskiego, żółtego i zielonego koloru.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wszystkie przyciski wyboru koloru działają? Czy wszystkie zmieniają kostium na odpowiedni kolor? Czy po zmianie wszystkie linie są w odpowiednim kolorze? Czy wszystkie kredki rysują czubkiem rysika?

Zapisz swój projekt.

##KROK 4: Rysowanie tylko wewnątrz danego obszaru

Obecnie możemy rysować po całej scenie, nie tylko po tablicy. Trzeba to naprawić. Chcemy, aby można było rysować tylko po tablicy, trzeba więc będzie pilnować, aby kredka nie wyszła poza dozwolony obszar (czyli tablicę).

Pamiętaj, że Scratch określa punkty korzystając ze współrzędnych na osiach x i y. Tablica, po której chcemy rysować, znajduje się pomiędzy punktem -230 a 230 na osi x i pomiędzy -120 a 170 na osi y. Możemy użyć te wartości w bloku __jeżeli__, aby sprawdzać, czy kursor myszy znajduje się w tym obszarze, zanim przesuniemy ołówek w jego kierunku.

Aby to zrobić, owiń istniejący blok __idź do... jeżeli__  w kolejny blok __jeżeli__, który będzie sprawdzał położenie kursora myszy. Współrzędne kursora na osi x powinny być większe -230 i mniejsze niż 230, a współrzędne na osi y powinny być większe niż -120 i mniejsze od 170.

__Uwaga__. Aby to zrobić, potrzebujesz użyć kilku bloków z operatorem __i__: jeden dla obu warunków dla współrzędnych na osi x, jeden dla obu warunków dla współrzędnych na osi y oraz jeden do połączenia wszystkich warunków ze sobą.

```scratch
	wyczyść
	zawsze
		jeżeli x myszy > -230 i x myszy < 230 i y myszy > -120 i y myszy < 170
		idź do wskaźnik myszy
```

Skoro nie możemy rysować poza wyznaczonym obszarem, byłoby dobrze chować kredkę, kiedy wyjdziemy poza tablicę. Aby to zrobić, zamień blok __jeżeli__ na blok __jeżeli... w przeciwnym przypadku__. Zostaw warunek, który masz w __jeżeli__ i __pokaż__ kredkę, kiedy to prawda i chowaj ją, kiedy warunek nie jest spełniony.

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

__Super, że możemy już rysować, ale przydałoby się dodać gumkę do poprawiania drobnych błędów.__ Możemy to zrobić dodając nową kredkę, który rysuje na szaro (czyli w tym samym kolorze, co tło).

Dodaj nowego duszka i wybierz dla niego kostium __gumka__ z katalogu Zasoby. Zmniejsz go, aby zmieścił się na dole ekranu i pasował do pozostałych przycisków. Nowy przycisk powinien działać tak samo, jak poprzednie i nadawać informacje, że jest gumką.

Duszek-kredka powinien reagować na wiadomość gumki i zmieniać kolor na szary (pamiętaj, że możesz użyć pipetę, aby wybrać odpowiedni kolor z tła). Duszek potrzebuje też nowy kostium – użyj tej samej gumki, co do przycisku wcześniej. __Pamiętaj, aby ustawić środek duszka na jego końcu__.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy gumka działa? Czy działa przy samych brzegach ekranu? Możesz przełączać się między gumką a kredkami?

Zapisz swój projekt.

##KROK 6: Pieczątka

Następną rzeczą, którą możemy dodać, jest pieczątka, przy pomocy której będziemy dodawać małe obrazki na tablicę.

1. Dodaj nowego duszka i wybierz mu taki kostium, jaki tylko chcesz. Zmniejsz go i ustaw na liście obok przycisków wyboru koloru. Po kliknięciu, duszek powinien nadawać wiadomość __pieczątka__.
2. Dodaj wybranego duszka jako nowy kostium dla kredki.
3. Zaznacz duszka-kredkę i dodaj do niej zmienną __rysowanie__. Zmienna powinna być dostępna tylko dla tego duszka. Będziemy jej używać do sprawdzania, czy rysujemy, czy też stawiamy pieczątki.
4. Dodaj skrypt, który odbiera wiadomość nadaną przez pieczątkę. Skrypt powinien zmieniać kostium kredki oraz ustawiać zmienną __rysowanie__ na __fałsz__.
5. Zmień pozostałe skrypty kredki, które reagują na wiadomości nadawane przez przyciski z tablicy, aby ustawiały zmienną __rysowanie__ na __prawda__.
6. Na koniec, sprawdzajmy tą zmienną __kiedy wciśnięty jest przycisk myszy__, aby się upewnić, czy powinniśmy rysować, czy stawiać pieczątki. Jeżeli rysowanie = prawda, powinniśmy używać bloku __przyłóż pisak__. Jeżeli nie, powinniśmy użyć bloku __stempluj__.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy pieczątka działa jak trzeba?

Co się dzieje, jeżeli przełączysz z powrotem na zwykłą kredkę?

Zapisz swój projekt.

__Brawo! Udało Ci się zakończyć podstawowe elementy tego projektu. Teraz spróbuj zmierzyć się z poniższymi wyzwaniami!__

##Wyzwanie 1: Tęczowa kredka

Dodajmy specjalną kredkę, który rysuje we wszystkich kolorach tęczy. Zwykłe kredki tego nie potrafią, więc masz teraz okazję pokazać, że rysowanie na komputerze pozwala robić rzeczy, które nie są normalnie możliwe. Aby to zrobić, musisz często zmieniać kolor kredki.

Na początek dodaj jednak przycisk wyboru tęczowego koloru i tęczowy kostium dla duszka-kredki:

1. Dodaj nowego duszka z wyborem koloru na dole tablicy, tuż obok innych przycisków. Skorzystaj z kostiumu 'teczowa kredka' z katalogu Zasoby i każ mu nadawać wiadomość __tęcza__ po kliknięciu.
2. Dodaj 'teczowa kredka' jako kostium do duszka ołówka.

Potrzebujesz zbudować skrypt, który będzie zmieniał kolor kredki wiele razy w ciągu sekundy, aby oddać efekt tęczy. Zmienianie koloru o 5 co 0,05 sekund działa całkiem dobrze, ale przetestuj inne wartości. Karta 'Timer' pokazuje, jak możesz zmieniać różne rzeczy co ileś sekund. Skorzystaj z bloku __zmień kolor pisaka o 5__ zamiast zmieniać licznik o -1 wewnątrz pętli.

Musisz też pilnować, aby ta pętla zmieniała kolory tylko wtedy, kiedy jest wybrana tęczowa kredka – w przeciwnym przypadku wszystkie kredki będą rysować na tęczowo! Możesz to zrobić w sposób podobny do tego, w który kontrolujesz, czy rysujesz, czy stawiasz pieczątki. Musisz stworzyć zmienną __pokażTęczę__, która ma wartość __prawda__ jeżeli chcesz rysować tęczę i wartość __fałsz__, jeżeli nie chcesz. Za każdym razem, gdy kredka reaguje na wiadomość odebraną od przycisku na dole tablicy, powinna ustawiać odpowiednią wartość dla zmiennej __pokażTęczę__.

Użyj przykładu z pieczątkami, aby nauczyć się kontrolować tęczę. Każdy skrypt, który reaguje na wiadomości nadawane przez przyciski wyboru na tablicy, będzie musiał ustawiać wartość dwóch zmiennych: rysowanie i pokażTęczę.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy rysowanie na tęczowo działa jak należy?

Co się dzieje, kiedy przełączasz się między tęczową kredką a pozostałymi narzędziami?

Zapisz swój projekt.

##Wyzwanie 2: Skróty klawiszowe

Zamiast klikać na przyciski na dole tablicy, możesz używać klawiatury, aby przełączać się pomiędzy różnymi narzędziami. Możesz skorzystać z bloku __naciśnięty klawisz []__, aby reagować na komendy klawiatury. Dla każdego skrótu, który chcesz użyć, potrzebujesz ustawić osobny blok __naciśnięty klawisz []__, który prześle tę samą wiadomość, którą nadałby kliknięty odpowiedni przycisk. Dodaj te skrypty do sceny.

My skorzystaliśmy z tych skrótów:
* Wyczyść wszystko - w
* Gumka - g
* Czerwony ołówek - c
* Niebieski ołówek - n
* Żółty ołówek - x
* Zielony ołówek - z 
* Tęczowy ołówek - t
* Pieczątka - p

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wszystkie skróty klawiszowe działają? Czy możesz wybierać wszystkie narzędzia przy pomocy klawiatury? Czy klikanie na przyciski na tablicy dalej działa?

Zapisz swój projekt.

##Wyzwanie 3: Różne rozmiary linii

Następną opcją, która jest dostępna w programach graficznych, jest możliwość zmieniania rozmiaru linii. Dodajmy to do naszego projektu.
Mamy jeden problem, z którym trzeba będzie się zmierzyć: zmiana rozmiaru czasami musi zmienić rozmiar kredki, a czasami rozmiar kostiumu duszka. Wszystko zależy od tego, czy rysujemy, czy też stawiamy pieczątki.

Stwórz dwa nowe duszki-przyciski na tablicy i nazwij je __powiększ__ i __pomniejsz__. Dodaj do nich odpowiednie kostiumy z katalogu Zasoby. Oba duszki powinny też nadawać odpowiednie wiadomości (powiększ i pomniejsz) po kliknięciu.

Duszek-kredka może reagować na te wiadomości na dwa sposoby: albo zmieniając rozmiar pisaka o 1, albo rozmiar kostiumu o 10, w zależności od wartości zmiennej __rysowanie__. Skorzystaj z bloku __jeżeli w przeciwnym przypadku__, aby to kontrolować – podobnie jak w przypadku wybierania między przyłożeniem pisaka a stawianiem pieczątek. Nie zapomnij dodać skrótów klawiszowych dla nowego narzędzia (my dodaliśmy strzałkę w górę i dół).

Zapisz swój projekt.

Pewnie udało Ci się zauważyć, że zmiana rozmiaru pieczątki zmienia też rozmiar duszka na ekranie, łączenie z kredkami. Aby tego uniknąć, musisz ustawiać rozmiar kostiumu na 100% za każdym razem, kiedy przełączasz się na kredkę. Pomoże to zachować odpowiedni rozmiar kredek. 

Możesz jeszcze bardziej ulepszyć swoje narzędzia, każąc pieczątce zapamiętać swój rozmiar, tak aby po przełączeniu się na kredkę czy gumkę można było wrócić do starego rozmiaru pieczątki. Najłatwiejszym rozwiązaniem jest dodanie zmiennej __rozmiarPieczątki__, która zapisuje obecny rozmiar pieczątki po każdej jego zmianie. Po ponownym wybraniu pieczątki, powinna ona odczytać tę zmienną i wybrać odpowiedni rozmiar.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy przyciski zmiany rozmiaru działają dla kredek?

Co się dzieje, kiedy przełączasz się na pieczątkę, zmieniasz jej rozmiar i przełączasz się na kredkę?

Zapisz swój projekt.

__Brawo! To by było na tyle, teraz możesz się cieszyć swoją grą!__
Nie zapomnij, że możesz podzielić się swoją grą ze swoimi przyjaciółmi i rodziną. Żeby to zrobić, kliknij menu __Udostępnij__.