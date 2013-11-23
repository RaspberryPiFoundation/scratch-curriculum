Poziom 1

#Fajerwerki

__Wstęp:__
Ta interaktywna zabawka pokazuje wybuchające fajerwerki i odtwarza dźwięk wybuchu przy każdym kliknięciu. 

##KROK 1: Stwórz rakietę, która leci w kierunku myszy

__Zaimportujmy wszystkie obrazki potrzebne do gry__

1. Zacznij nowy projekt w Scratchu. Skasuj kota, klikając na nim prawym przyciskiem myszki i wybierając Usuń.
2. Zmień tło na "city-with-water" z katalogu Outdoor.
3. Użyj przycisku __"Wybierz nowego duszka z pliku"__, aby dodać rakietę. Otwórz katalog Zasoby i wybierz plik rakieta.png. Zmień nazwę duszka na Rakieta.
4. Spraw, aby rakieta się chowała po wciśnięciu zielonej flagi.

Teraz chcemy, aby rakieta leciała w kierunku kursora myszki po kliknięciu.

5. Dodaj blok "kiedy klawisz spacja naciśnięty" do skryptu, a pod nim dodaj skrypt pokazujący rakietę ponownie i sprawiający, że leci w kierunku kursora.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj

	kiedy klawisz spacja naciśnięty	
	pokaż	
	leć przez 1 s to x: x myszy y: y myszy
```
		
###Przetestuj swój projekt
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__

Czy rakieta się pojawia i przesuwa w kierunku myszy?
Co się dzieje, jak ruszysz myszą i wciśniesz spację ponownie?

6. Fajerwerki nie latają w bok, więc upewnijmy się, że za każdym razem rakieta będzie lecieć do góry z dołu ekranu. Zanim pokażemy rakietę, ustawmy, aby przesuwała się pod spód ekranu, ale aby była poziomo w tym samym miejscu.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	
	kiedy klawisz spacja naciśnięty	
	idź do x: x myszy y: -200	
	pokaż	
	leć przez 1 s to x: x myszy y: y myszy
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, ustaw kursor myszy na Scenie i wciśnij spację.__
Czy rakieta leci w kierunku kursora z samego dołu ekranu? Co się dzieje, jeśli przesuniesz kursor i wciśniesz spację ponownie?

7. Pora zamienić spację na klik myszki. Aby to zrobić, możemy owinąć nasz skrypt w blok "__zawsze, jeżeli wciśnięty klawisz myszy__". Później można zamienić blok "kiedy klawisz spacja naciśnięty" na "__kiedy kliknięto FLAGĘ__". Pamiętaj, żeby rakieta była ukryta, kiedy wszystko się zaczyna.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?	
		idź do x: x myszy y: -200	
		pokaż	
		leć przez 1 s to x: x myszy y: y myszy	
	(koniec zawsze)
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, a następnie kliknij na scenie. Kliknij jeszcze raz w innym miejscu.__

###Rzeczy do spróbowania
1. Spróbuj zmienić gdzie ustawia się rakieta zanim zacznie lecieć w stronę myszy, aby dodać lekki łuk do toru jej lotu.
2. Spróbuj zmienić prędkość rakiet: niech niektóre lecą szybciej lub wolniej niż inne.

Zapisz swój projekt.

##KROK 2: Spraw, aby rakiety wybuchały

1. Pierwszym krokiem do wybuchających rakiet jest dodanie odgłosu wystrzału zanim rakieta zacznie się ruszać, a potem schowanie jej zanim doleci do kursora. Aby zaimportować odgłos wybuchu, przejdź do karty Dźwięki i wybierz plik "bum" z katalogu Zasoby.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?	
		idź do x: x myszy y: -200		
		zagraj dźwięk bum	
		pokaż	
		leć przez 1 s to x: x myszy y: y myszy		
		ukryj	
	(koniec zawsze)
```

2. Następnie, dodaj nadawanie komunikatu przez rakietę, kiedy eksploduje. Będziemy słuchać tego komunikatu trochę później.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?	
		idź do x: x myszy y: -200		
		zagraj dźwięk bum	
		pokaż	
		leć przez 1 s to x: x myszy y: y myszy		
		ukryj		
		nadaj wybuch	
	(koniec zawsze)
	
```
###Przetestuj swój projekt
__Kliknij zieloną flagę.__
Upewnij się, że rakieta odtwarza dźwięk i ukrywa się, gdy dolatuje do kursora.

3. Dodaj nowego duszka i wybierz plik fajerwerki1.png z katalogu Zasoby.
4. Kiedy nowy duszek odbierze komunikat o wybuchu, powinien się ukryć i przesunąć w miejsce, w którym jest rakieta, korzystając z bloku "idź do". Następnie powinien się pokazać w nowym miejscu i zniknąć ponownie sekundę później.

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
Czy została zastąpiona grafiką wybuchu?
Co się dzieje, jeżeli trzymasz wciśnięty przycisk myszy i przesuwasz kursor? (Nie martw się, naprawimy to później)

Zapisz swój projekt.

##KROK 3: Spraw, aby każda eksplozja była unikalna

1. Teraz możemy sprawić, aby każdy wybuch był unikalny i wyjątkowy. Skorzystaj z bloku "zmień efekt kolor" i każ mu wybierać losowy kolor z listy od 1 do 200 przed pokazaniem wybuchu.

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

2. Dodajmy kilka różnych rodzajów eksplozji. Zaimportuj pliki fajerwerki2.png i fajerwerki3.png z katalogu Zasoby jako kostiumy i dodaj przełączanie między nimi dla każdej rakiety tuż przed pokazaniem jej.

###Przetestuj swój projekt
__Kliknij zieloną flagę.__

Czy każda rakieta wybucha w inny sposób i ma inny kolor?

3. Na koniec dodamy rosnące wybuchy zamiast po prostu sprawiać, że eksplozja pojawia się na ekranie. Zamiast czekać sekundę, ustaw rozmiar duszka na 5% zanim zostanie pokazany, a potem, jak już będzie widoczny, skorzystaj z bloku "powtórz", aby zwiększyć jego rozmiar o 2 pięćdziesiąt razy.

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

Czy wybuch rozszerza się z centrum rakiety i powoli rośnie?

###Rzeczy do spróbowania
Spróbuj sprawić, aby każdy wybuch był bardziej unikalny, zmieniając jego rozmiar i szybkość wzrostu każdej eksplozji.

Zapisz swój projekt.

##KROK 4: Naprawiamy problem z nadawaniem komunikatu
Pamiętasz błąd, jaki pojawił się wcześniej przy ruszaniu kursora podczas gdy przycisk myszy jest wciśnięty?
Dzieje się tak, ponieważ kiedy rakieta nadaje komunikat o wybuchu, powtarza ona natychmiast pętlę "jeżeli" i nadaje kolejny komunikat jeszcze zanim ten ostatni skończył być wyświetlany.

1. Aby to naprawić, możemy zastąpić blok "nadaj" blokiem "nadaj i czekaj", przez co pętla nie powtórzy się, dopóki wybuch się nie skończy.

```scratch

	kiedy kliknięto FLAGĘ
	ukryj
	zawsze, jeżeli wciśnięty klawisz myszy?	
		idź do x: x myszy y: -200		
		zagraj dźwięk bum	
		pokaż	
		leć przez 1 s to x: x myszy y: y myszy		
		ukryj		
		nadaj wybuch i czekaj	
	(koniec zawsze)
	
```

###Przetestuj swój projekt
__Kliknij zieloną flagę, przytrzymaj przycisk myszy i przesuń kursor po ekranie.__

Czy grafika eksplozji pojawia się teraz w odpowiednim miejscu i we właściwym czasie? 

Zapisz swój projekt.