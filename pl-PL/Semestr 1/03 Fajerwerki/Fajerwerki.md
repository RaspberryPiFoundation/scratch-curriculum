Poziom 1

#Fajerwerki

__Wstęp:__
Ta interaktywna zabawka pokazuje wybuchające fajerwerki i odtwarza dźwięk wybuchu przy każdym kliknięciu.

##KROK 1: Stwórz rakietę, która leci w kierunku kursora myszki

__Zaimportujmy wszystkie obrazki potrzebne do gry__

1. Rozpocznij nowy projekt w Scratchu. Usuń kota, klikając na nim prawym przyciskiem myszki i wybierając „usuń”.
2. Zmień tło na „city-with-water” z katalogu „Outdoor”.
3. Użyj przycisku __„Wybierz nowego duszka z pliku”__, aby dodać rakietę. Otwórz katalog „Zasoby” i wybierz plik „rakieta.png”. Zmień nazwę duszka na „Rakieta”.
4. Spraw, aby rakieta zniknęła po wciśnięciu zielonej flagi.

Teraz sprawimy, aby po klinięciu rakieta poleciała w kierunku kursora myszki.

5. Dodaj blok „kiedy klawisz spacja naciśnięty” do skryptu, a pod nim dodaj skrypt pokazujący ponownie rakietę i sprawiający, że poleci ona w kierunku kursora myszy.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj

	kiedy klawisz spacja naciśnięty
	pokaż
	leć przez 1 s do x: x myszy y: y myszy
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__

Czy rakieta pojawia się na ekranie i leci w kierunku kursora myszy?

Co się dzieje, kiedy poruszysz myszą i wciśniesz spację ponownie?

1. Fajerwerki nie latają na boki, więc upewnijmy się, że za każdym razem rakieta leci prosto do góry. Zanim pokażemy rakietę na ekranie, użyjmy bloku „idź do”, aby ustawić ją pionowo na dole ekranu.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj

	kiedy klawisz spacja naciśnięty
	idź do x: x myszy y: -200
	pokaż
	leć przez 1 do to x: x myszy y: y myszy
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__

Czy rakieta leci w kierunku kursora z samego dołu ekranu?

Co się dzieje, kiedy przesuniesz kursor w bok i wciśniesz spację ponownie?

1. Pora zamienić naciśnięcie klawisza spacji na kliknięcie klawiszem myszki. Aby to zrobić, „owińmy” nasz skrypt w blok __„zawsze, jeżeli wciśnięty klawisz myszy”__, a następnie zastąpmy blok „kiedy klawisz spacja naciśnięty” blokiem __„kiedy kliknięto FLAGĘ”__. Pamiętaj, żeby na początku gry rakieta była zawsze ukryta.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?
		idź do x: x myszy y: -200
		pokaż
		leć przez 1 s do x: x myszy y: y myszy
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, a następnie kliknij na scenie. Kliknij jeszcze raz w innym miejscu.__

###Rzeczy do spróbowania
1. Spróbuj zmienić cel rakiety, zanim zacznie lecieć w stronę myszy. (Tak aby leciała lekko po łuku.)
2. Spróbuj zmienić prędkość rakiety: niech niektóre lecą szybciej, a inne wolniej.

Zapisz swój projekt.

##KROK 2: Spraw, aby rakieta wybuchła

1. Pierwszym zadaniem dla nas będzię dodanie odgłosu huku tuż przed wylotem rakiety oraz schowanie jej, gdy doleci do celu. Aby zaimportować odgłos wybuchu, przejdź do zakładki „Dźwięki” i wybierz plik „bum” z katalogu Zasoby.

    ```scratch

        kiedy kliknięto FLAGĘ
        ukryj
        zawsze, jeżeli wciśnięty klawisz myszy?
            idź do x: x myszy y: -200
            zagraj dźwięk bum
            pokaż
            leć przez 1 s do x: x myszy y: y myszy
            ukryj
        (koniec zawsze)
    ```

2. Następnie nadajmy komunikat eksplozji rakiety. Odbierzemy go troszkę później.

    ```scratch

        kiedy kliknięto FLAGĘ
        ukryj
        zawsze, jeżeli wciśnięty klawisz myszy?
            idź do x: x myszy y: -200
            zagraj dźwięk bum
            pokaż
            leć przez 1 s do x: x myszy y: y myszy
            ukryj
            nadaj wybuch
        (koniec zawsze)
    ```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Upewnij się, że rakieta odtwarza dźwięk i chowa się po osiągnięciu celu.

1. Dodaj nowego duszka i wybierz plik „fajerwerki1.png” z katalogu „Zasoby”.
2. Kiedy nowy duszek odbierze komunikat o wybuchu, powinien się ukryć i przesunąć w miejsce, w którym jest rakieta – użyj do tego bloku „idź do”. Następnie powinien się pokazać w nowym miejscu i zniknąć ponownie sekundę później.

```scratch

	kiedy otrzymam wybuch
	ukryj
	idź do x: współrzędna x z Rakieta y: współrzędna y z Rakieta
	pokaż
	czekaj 1 s
	ukryj
```

###Przetestuj swój projekt
__Wystrzel następną rakietę.__

Czy rakieta została zastąpiona obrazkiem wybuchu?

Co się dzieje, kiedy przytrzymasz wciśnięty przycisk myszy i przesuwasz kursor? (Nie martw się, naprawimy ten problem później).

Zapisz swój projekt.

##KROK 3: Spraw, aby każda eksplozja była unikalna

1. Teraz sprawmy, aby każdy wybuch był inny. Skorzystaj z bloku „zmień efekt kolor” i każ mu wybierać losowy kolor z listy od 1 do 200 przed pokazaniem wybuchu.

```scratch

	kiedy otrzymam wybuch
	ukryj
	zmień efekt kolor na losuj liczbę pomiędzy 1 a 200
	idź do x: współrzędna x z Rakieta y: współrzędna y z Rakieta
	pokaż
	czekaj 1 s
	ukryj
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy każda eksplozja ma inny kolor?

1. Dodajmy kilka różnych rodzajów eksplozji. Zaimportuj pliki „fajerwerki2.png” i „fajerwerki3.png” z katalogu „Zasoby” jako nowe kostiumy i dodaj przełączanie między nimi dla każdej rakiety tuż przed jej pokazaniem się.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy każda rakieta wybucha w inny sposób i ma inny kolor?

1. Na koniec sprawmy, aby każda eksplozja powiększała się w miarę upływu czasu, a nie po prostu pojawiała się na ekranie. Zamiast czekać sekundę, ustaw rozmiar duszka na 5% zanim zostanie pokazany, a potem, jak już będzie widoczny, skorzystaj z bloku „powtórz”, aby zwiększyć jego rozmiar o 2 pięćdziesiąt razy.

```scratch

	kiedy otrzymam wybuch
	ukryj
	zmień efekt kolor na losuj liczbę pomiędzy 1 a 200
	idź do x: współrzędna x z Rakieta y: współrzędna y z Rakieta
	ustaw rozmiar na 5%
	pokaż
	powtórz 50 razy
		zmień rozmiar o 2
	(koniec powtórz)
	ukryj
```

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy wybuch rakiety powiększa się w miarę upływu czasu?

###Rzeczy do spróbowania
Spróbuj sprawić, aby każdy wybuch był bardziej unikalny, zmieniając jego rozmiar i szybkość wzrostu każdej eksplozji.

Zapisz swój projekt.

##KROK 4: Naprawiamy problem z nadawaniem

Pamiętasz błąd, który pojawił się wcześniej przy poruszaniu kursora myszy, gdy przycisk myszy jest wciśnięty?

Dzieje się tak z dlatego, że rakieta nadaje komunikat o wybuchu i natychmiast powtarza pętlę „jeżeli”, która z kolei nadaje kolejny komunikat o wybuchu, zanim ten poprzedni skończył się wyświetlać.

1. Aby to naprawić, możemy zastąpić blok „nadaj” blokiem „nadaj i czekaj”, przez co pętla nie powtórzy się, dopóki wybuch się nie skończy.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?
		idź do x: x myszy y: -200
		zagraj dźwięk bum
		pokaż
		leć przez 1 s do x: x myszy y: y myszy
		ukryj
		nadaj wybuch i czekaj
	(koniec zawsze)

```

###Przetestuj swój projekt
__Kliknij zieloną flagę, przytrzymaj przycisk myszy i przesuń kursor po ekranie.__

Czy obrazek eksplozji pojawia się teraz w odpowiednim miejscu i we właściwym czasie?

Zapisz swój projekt.
