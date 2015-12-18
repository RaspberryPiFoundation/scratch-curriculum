---
title: Boat Race
level: Scratch 1
language: ro-RO
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*.*","Project Resources/*.*"]
...

# Introducere { .intro }

Vei învăța cum să creezi un joc în care vei utiliza mouse-ul ca să navighezi o barcă înspre o insulă pustie.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/63957956/?autostart=false" frameborder="0"></iframe>
  <img src="boat-final.png">
</div>

# Pasul 1: Planifică jocul { .activity }

## Lista de activități { .check }

+ Deschide un nou proiect în Scratch și șterge sprite-ul pisică. În acest fel ai un proiect gol. Poți să găsești editorul online pentru Scratch la <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Click pe scenă și planifică nivelul de dificultate. Ar trebui să adaugi:
	+ Bușteni pe care barca ta trebuie să le ocolească;
	+ O insulă pustie la care barca trebuie să ajungă.

	Jocul ar trebui să arate cam așa: 

	![screenshot](boat-bg.png) 

# Pasul 2: Controlul bărcii { .activity }

## Lista de activități { .check }

+ Dacă ați primit un folder cu resurse click 'Incarca sprite din fisier' și selectează imaginea 'boat.png'. Trebuie să micșorezi sprite-ul și să-l pui în poziția de plecare. 

	![screenshot](boat-boat.png)

	Dacă nu ai imaginea boat.png, poți să-ți desenezi singur barca!

+ Vei controla barca cu mouse-ul. Adaugă codul de mai jos la barcă:

	```blocks
		cand se da clic pe flag
		orienteaza in directia (0 v)
		du-te la x: (-190) y: (-150)
		la infinit
			orienteaza inspre [cursorul mouse-ului v]
			muta (1) pasi
		end
	```

+ Testează-ți barca. Fă clic pe steag și mișcă mouse-ul. Barca se îndreaptă înspre mouse? 

	![screenshot](boat-mouse.png)

+ Ce se întâmplă dacă barca atinge vârful mouse-ului? 

	Pentru a rezolva problema, trebuie să adaugi un bloc `dacă` {.blockcontrol} la codul tău. În acest fel barca se va mișca numai dacă este la mai mult de 5 pixeli de mouse. 

	![screenshot](boat-pointer.png)	

+ Testează-ți barca din nou. Verifică dacă problema a fost rezolvată.

## Salvează proiectul { .save }

# Pasul 3: Accident! { .activity .new-page }

Barca poate naviga prin barierele de bușteni! Haideți să rezolvăm problema aceasta.

## Lista de activități { .check }

+ Vei avea nevoie de două costume pentru barca ta, un costum normal și unul pentru momentul când barca are un accident. Copiază costumul barcă. Redenumește-le 'normal' și 'lovit'.

+ Clic pe costumul 'lovit' și alege unealta 'Selecteaza' pentru a captura bucățele de barcă. Mută-le și rotește-le. Încearcă să creezi o barcă care arată ca după un accident.

	![screenshot](boat-hit-costume.png)

+ Adaugă codul de mai jos la scriptul bărcii în blocul `forever` {.blockcontrol}. Barca va avea un accident când atinge orice buștean:

	```blocks
		dacă <atinge culoarea [#603C15]?> atunci
			switch costume to [lovit v]
			spune [Noooooo!] pentru (1) sec
			switch costume to [normal v]
			orienteaza in directia (0 v)
			du-te la x: (-215) y: (-160)
		end
	```

	Acest cod este inclus în bucla `la infinit` {.blockcontrol} astfel încât codul tău va continua să verifice dacă barca are vreun accident.

+ Ar trebui să ai grijă ca barca să arate 'normal' de fiecare dată când începi un joc nou.
 
+ Acum, dacă încerci să navighezi printr-o barieră de bușteni, ar trebui să vezi că barca s-a accidentat și o ia de la început.

	![screenshot](boat-crash.png)

## Salvează proiectul { .save }

## Provocare: Câștigă! {.challenge}
Poți să adaugi o comandă `dacă` {.blockcontrol} la codul bărcii, pentru ca jucătorul să câștige când ajunge la insula pustie?

Când barca ajunge la insula pustie, ar trebui să spună 'URA!' și jocul trebuie să ia sfârșit. Trebuie să utilizezi codul următor:

```blocks
	spune [URA!] pentru (1) sec
	opreste [tot v]
```

![screenshot](boat-win.png)

## Salvează proiectul { .save }

## Provocare: Efecte de sunet {.challenge}
Poți sa adaugi efecte de sunet pentru momentul când barca se accidentează sau când ajunge la insulă. Poți să adaugi și fundal sonor (vezi proiectul anterior 'Rock Band' dacă ai nevoie de ajutor).

## Salvează proiectul { .save }

# Pasul 4: Contra Cronometru { .activity }

Haideți să adăugăm un cronometru la joc, pentru ca jucătorul să încerce să ajungă la insula pustie cât mai repede.

## Lista de activități { .check }

+ Adaugă la scenă o nouă variabilă numită `timp` {.blockdata}.

	![screenshot](boat-variable.png)

+ Adaugă codul de mai jos la __scena__ ta, astfel încât să poți cronometra cât de repede ajungi la insula pustie:

	```blocks
		cand se da clicl pe flag
		seteaza [timp v] la [0]
		la infinit
			asteapta (0.1) sec
			modifică [timp v] cu (0.1)
		end
	```

+ Atât! Testează jocul și vezi cât de repede reușești să ajungi la insula pustie!

	![screenshot](boat-variable-test.png)

## Salvează proiectul { .save }

# Pasul 5: Obstacole și 'acceleatori' { .activity }

Jocul este mult prea simplu. Hai să adăugăm lucruri ca să-l facem mai interesant.

## Lista de activități { .check }

+ Pentru început putem adăuga 'acceleratori' care vor face barca să navigheze mai repede. Editează fundalul scenei și adaugă săgeți albe de accelerare.

	![screenshot](boat-boost.png)

+ Acum poți să adaugi în scriptul bărcii cod la bucla `la infinit` {.blockcontrol}, astfel încât barca se va muta doi pași când atingi un accelerator alb.

	```blocks
		dacă <atinge culoarea [#FFFFFF]?> atunci
			muta (3) pasi
		end
	```

+ Poți adăuga o poartă care se rotește pe care barca trebuie să o ocolească. Adaugă un sprite nou numit 'poartă', care arată cam așa:

	![screenshot](boat-gate.png)

	Ai grijă ca poarta să aibă aceeași culoare ca și buștenii.

+ Setează centrul pentru sprite-ul poartă.

	![screenshot](boat-center.png)

+ Adaugă cod pentru sprite-ul poartă pentru a o face să se rotească încet `la infinit` {.blockcontrol}.

+ Testează jocul. Ar trebui să ai acum o poartă care se rotește pe care trebuie să o ocolești.

	![screenshot](boat-gate-test.png)

## Salvează proiectul { .save }

## Provocare: Mai multe obstacole! {.challenge .new-page}
Poți să adaugi mai multe obstacole la joc? Mai jos câteva idei:

+ Poți să adaugi mâzgă verde care va încetini jucătorul dacă o atinge. Poți să utilizezi blocul `asteapta` {.blockcontrol}:

```blocks
	asteapta (0.01) sec
````

![screenshot](boat-algae.png)

+ Poți să adaugi obiecte mișcătoare, de exemplu un buștean sau un rechin!

![screenshot](boat-obstacles.png)

Blocul de cod de mai jos ți-ar putea fi de ajutor:

```blocks
	muta (1) pasi
	daca se afla pe margine, ricoseaza
````

Dacă noul obiect nu este maro, trebuie să adaugi codul următor la scriptul bărcii:

```blocks
	dacă <  <atinge culoarea [#603C15]?> sau <touching [rechin v]?> > atunci
	end
```

## Salvează proiectul { .save }

## Provocare: Mai multe bărci! {.challenge .new-page}
Poți schimba jocul într-o cursă între doi jucători?

+ Copiază barca, denumește-o 'Jucător 2' și schimbă-i culoarea.

![screenshot](boat-p2.png)

+ Schimbă poziția de start pentru al doilea jucător schimbând următorul cod:

```blocks
	du-te la x: (-190) y: (-150)
```

+ Șterge codul care utilizează mouse-ul pentru controlul bărcii:

```blocks
	dacă < (distanța până la [cursorul mouse-ului v]) > [5] > atunci
		orienteaza inspre [cursorul mouse-ului v]
		muta (1) pasi
	end
```

...și în loc lui adaugă codul următor pentru a controla barca cu tastele săgeți.

Acesta este codul de care vei avea nevoie pentru a avansa barca înainte:

```blocks
	dacă < tasta [sageata sus v] este apasata? > atunci
		muta (1) pasi
	end
```

De asemenea vei avea nevoie de cod pentru a `roti` {.blockmotion} barca atunci când tastele ’săgeată stânga’ și ’săgeată dreapta’ sunt apăsate.

## Salvează proiectul { .save }

## Provocare: Mai multe nivele! {.challenge .new-page}
Poți crea scene noi și să-i lași pe jucători să aleagă între nivele?

```blocks
	cand tasta [spatiu v] este apasata
	urmatorul fundal
```

## Salvează proiectul { .save }

## Community Contributed Translation { .challenge .pdf-hidden }

This project was translated by Elena-Georgeta Popa. Our amazing translation volunteers help us give children around the world the chance to learn to code.  You can help us reach more children by translating a Code Club project via [Github](https://github.com/CodeClub/curriculum_documentation/blob/master/contributing.md) or by getting in touch with us at hello@codeclubworld.
