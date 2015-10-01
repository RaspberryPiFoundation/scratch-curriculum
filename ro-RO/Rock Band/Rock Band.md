---
title: Rock Band
level: Scratch 1
language: ro-RO
stylesheet: scratch
embeds: "*.png"
...

# Introducere { .intro }

In acest proiect vei invata sa creezi propiul tau instrument muzical!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>

# Pasul 1: Sprites { .activity }

Inainte sa incepi sa animezi ai nevoie sa alegi un "actor" pe care sa-l
controlezi. In Scratch, aceste "caractere" se numesc __sprites__. 

## Lista de Activitati { .check }

+ Pentru inceput, deschide editorul de Scratch. Il poti vedea online la <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. Arata cam asa:

	![screenshot](band-scratch.png)

+ Sprite-ul pisica pe care il vezi este mascota Scratch. Haide sa-l stergem. Click dreapta pe mouse si dupa aceea pe ?delete?.

	![screenshot](band-delete.png)

+ Dupa aceea selecteaza ?Choose sprite from library' ca sa deschizi o lista cu toate caracterele din Scratch.

	![screenshot](band-sprite-library.png)

+ Du-te mai jos pana cand vei vedea un ?sprite? toba (drum
in engleza). Selecteaza-l si apasa ?OK? ca sa-l aduci in
proiectul tau.

	![screenshot](band-sprite-drum.png)

+ Apasa pe ?shrink' icon (micsorare), apoi pe toba de cateva ori sa o faci
mai mica.

	![screenshot](band-shrink.png)

## Salveaza proiectul { .save }

Da-i programului tau un nume. Scrie numele nou in fereastra de
deasupra scenei.

Poti sa faci click pe ?File' si apoi pe ?Save now' ca sa-ti salvezi proiectul.

![screenshot](band-save.png)

# Pasul 2: Scena { .activity }

__Scena__ este aria din stanga si este locul unde proiectul tau prinde viata.

## Lista de Activitati { .check }

+ La inceput scena este goala si arata cam plictisitor! Haide sa-i punem un fundal. Selecteaza: 'Choose backdrop from library'.

	![screenshot](band-stage-choose.png)

+ Click pe ?Indoors? (asta inseamna "Interioare" in engleza)/ Fa click pe seciunea 'Indoors' (interior), apoi pe fundalul pe care vrei sa-l alegi pentru scena si apoi pe 'OK'

	![screenshot](band-backdrop.png)

+ Scena ta ar trebui sa arate asa:

	![screenshot](band-stage.png)

# Pasul 3: Construind o Toba { .activity }

Haide sa scriem un script pentru toba. Vrem ca ea sa scoata un sunet cand este atinsa.

## Lista de Activitati { .check }

+ Vei gasi script-urile in sectiunea ?Scripts?. Toate script-urile sunt grupate pe module reprezentate prin aceeasi culoare.
De exemplu toate script-urile care controleaza sunetul au culoarea mov si se afla in grupul ?sound?! 

Fa click pe sprite-ul toba si muta cele doua script-uri in aria
de cod din dreapta avand grija sa le conectezi impreuna (ca
niste caramizi Lego):

	![screenshot](band-code.png)

+ Fa click pe toba sa incerci noul tau instrument muzical!

+ Poti sa schimbi si cum arata toba cand o bati. Pentru asta trebuie sa creezi un costum nou. Apasa pe sectiunea ?Costumes', si vei vedea imaginea tobei.

	![screenshot](band-drum-costume.png)

+ Click-dreapta pe mouse pe costum si apoi click ?duplicate' ca sa creezi o copie a costumului.

	![screenshot](band-drum-duplicate.png)

+ Selecteaza costumul nou (numit ?drum2'), iar apoi selecteaza "line tool" si deseneaza cateva linii ca si cum toba arata ca scoate un sunet.

	![screenshot](band-drum-hit.png)

+ Numele costumelor nu sunt foarte clare. Haide sa le schimbam cu "not hit" si "hit". Uita-te la imaginea de mai jos.

	![screenshot](band-drum-name.png)

+ Acum daca ai doua costume pentru toba, poti sa alegi ce costum vrei sa arati! Adauga aceste doua blocuri la script-ul tau:

	![screenshot](band-looks.png)

	Blocul de cod pentru schimbarea costumelor se gaseste in sectiunea `Looks` {.blocklooks}.

+ Testeaza-ti toba. Cand o atingi, toba ta ar trebui sa para ca scoate un sunet!

## Salveaza proiectul { .save }

##Exercitiu: Sa imbunatatim toba { .challenge }

+ Poti sa schimbi sunetul scos de toba atunci cand faci click pe ea?

![screenshot](band-drum-sound.png)

+ Poti sa faci toba sa sune si atunci cand apesi tasta spacebar? Va trebui sa folosesti acest bloc eveniment `event` {.blockevents}:

```blocks
	when [space v] key pressed
```

Poti refolosi codul deja existent daca faci click dreapta pe el si apoi alegi optiunea 'duplicate'.

![screenshot](band-duplicate-code.png)

## Salveaza proiectul { .save }

# Pasul 4: Sa construim un cantaret { .activity .new-page }

Hai sa adaugam un cantaret in formatia noastra!

## Lista de Activitati { .check }

+ Adauga inca 2 sprites pe scena ta; un cantaret si un microfon.

	![screenshot](band-singer-mic.png)

+ Inainte sa il poti face pe cantaret sa cante, trebuie sa ii adaugam un sunet sprite-ului tau. 
Dupa ce ai selectat cantaretul fa click pe tab-ul "Sounds" si apoi pe optiunea 'Choose sound from library', care ne permite sa alegem un sunet din biblioteca de fisiere:

	![screenshot](band-import-sound.png)

+ Daca faci click pe sectiunea 'Vocals' din partea stanga, vei putea apoi alege un sunet potrivit pentru sprite-ul tau.

	![screenshot](band-choose-sound.png)

+ Acum ca am adaugat sunetul, putem adauga acest cod cantaretului nostru:

	```blocks
		when this sprite clicked
		play sound [singer1 v] until done
	```

+ Fa click pe cantaretul tau pentru a verifica daca acesta canta atunci cand apasam pe el.

## Salveaza proiectul { .save }

##Exercitiu: Sa schimbam costumul cantaretului { .challenge }
Vrem ca atunci cand facem click pe cantaret, sa vedem ca acesta canta. Poti face asta? Daca ai nevoie de ajutor poti folosi instructiunile de la pasul 3 "Construind o toba".

![screenshot](band-singer-final.png)

Nu uita sa testezi ca noul tau cod functioneaza corect!

## Salveaza proiectul { .save }

##Exercitiu: Creaza propria ta formatie { .challenge }
Poti folosi ceea ce ai invatat in acest proiect pentru a crea propria ta formatie muzicala!
Poti crea orice instrument doresti, dar ca sa iti faci intai o idee, arunca o privire asupra sunetelor si instrumentelor disponibile in Scratch.

![screenshot](band-ideas.png)

Instrumentele nu trebuie sa fie neaparat reale. De exemplu, ai putea sa construiesti un pian din briose!

![screenshot](band-piano.png)

Pe langa sprite-urile existente, poti de asemenea sa desenezi unele noi.

![screenshot](band-draw.png)

Daca ai un microfon poti sa inregistrezi sunetele tale, sau poti folosi un webcam pentru a interactiona cu instrumentele.


![screenshot](band-io.png)

## Salveaza proiectul { .save }

