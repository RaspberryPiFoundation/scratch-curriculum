---
title: Catch the Dots
level: Scratch 2
language: ro-RO
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*", "Project Resources/*"]
beta: true
...

# Introducere { .intro }

În acest proiect vei învăța cum să creezi un joc în care în care trebuie să potrivești punctele colorate cu partea corectă a controlerului.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/44942820/?autostart=false" frameborder="0"></iframe>
  <img src="dots-final.png">
</div>

# Pasul 1: Crează controlerul { .activity }

Haide să începem prin a crea controlerul care va fi folosit pentru a colecta punctele.

## Lista de activități { .check }

+ Începe un nou proiect Scratch și șterge sprite-ul pisică. Poți găsi editorul de Scratch online la <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.

+ Dacă liderul clubului ți-a dat un director numit 'Resurse', click pe 'Upload sprite from file' și atașează imaginea 'controller.svg'. Mută sprite-ul în centrul scenei.

	![screenshot](dots-controller.png)
	
	Dacă nu ai imaginea, poți să desenezi un controler singur!
	
+ Îndreaptă controlerul înspre dreapta când tasta săgeată-dreapta este apăsată:

	```blocks
		when flag clicked
		forever
			if <key [right arrow v] pressed?> then
				turn right (3) degrees
			end
		end
	```
+ Testează controlerul – ar trebui să se învârtă înspre dreapta.

## Salvează proiectul { .save }

## Provocare: Învârte înspre stânga {.challenge}
Poți să învârți controlerul înspre stânga când săgeata-stângă este apăsată?

## Salvează proiectul { .save }

# Pasul 2: Colectează puncte { .activity }

Haide să adăugăm câteva puncte pe care jucătorul le va colecta cu ajutorul controlerului.

## Lista de activități { .check }

+ Crează un nou sprite numit 'roșu'. Acest sprite trebuie să fie un mic punct roșu.

	![screenshot](dots-red.png)

+ Adaugă scriptul de mai jos la sprite-ul 'roșu', pentru a crea un nou punct la un interval de câteva secunde:

	```blocks
		when flag clicked
		wait (2) secs
		forever
			create clone of [myself v]
			wait (pick random (5) to (10)) secs
		end
	```

+ Când fiecare clonă a fost creată, vei vrea să apară în unul din cele 4 colțuri ale scenei.

	![screenshot](dots-start.png)

	Pentru aceasta, în primul rând vei crea o nouă listă numită `start positions` {.blockdata} și apasă pe `(+)` pentru a adăuga valorile `-180` și `180`.

	![screenshot](dots-list.png)

+ Poți utiliza aceste două valori pentru a alege un colț aleator al scenei. Adaugă codul de mai jos la sprite-ul "dot", astfel încât fiecare nouă clonă se mută aleatoriu într-un colț și apoi încet se mișcă spre controler.

	```blocks
		when I start as a clone
		go to x: (item (random v) of [start positions v]) y: (item (random v) of [start positions v])
		point towards [controller v]
		show
		repeat until <touching [controller v]?>
			move (1) steps
		end
	```

	Codul de mai sus alege fie `180` sau `-180` pentru pozițiile x și y, ceea ce înseamnă că fiecare clonă începe într-un colț al scenei.

+ Testează proiectul. Ar trebui să vezi multe puncte roșii care apar în fiecare colt al ecranului și coboară încet înspre controler.

	![screenshot](dots-red-test.png)

+ Creează două noi variabile `vieți` {.blockdata} și `scor` {.blockdata}.

+ Adaugă cod la scenă pentru a seta variabila `vieți` {.blockdata} la 3 și `scor` {.blockdata} la 0 la începutul jocului.

+ Trebuie să adaugi cod la sfârșitul blocului `when I start as a clone` {.blockcontrol} în cadrul scriptului pentru sprite-ul `roșu`, astfel încât să crească scorul cu 1 dacă se potrivesc culorile, sau scade numărul de vieți cu 1 în cazul în care culorile nu se potrivesc.

	```blocks
		move (5) steps
		if <touching color [#FF0000]?> then
			change [score v] by (1)
			play sound [pop v]
		else
			change [lives v] by (-1)
			play sound [laser1 v]
		end
		delete this clone
	```

+ Adaugă codul de mai jos la sfârșitul scriptului scenei astfel încât jocul se termină dacă jucătorul a pierdut toate cele 3 vieți.:

	```blocks
		wait until <(lives) < [1]>
		stop [all v]
	```

+ Testează jocul și vezi dacă funcționează cum te-ai așteptat.

## Salvează proiectul { .save }

## Provocare: Mai multe puncte {.challenge}
Duplică sprite-ul roșu de două ori și denumește noile sprite-uri 'galben' și 'albastru'.

![screenshot](dots-more-dots.png)

Editează aceste sprite-uri (inclusiv codul), astfel încât fiecare punct se potrivește cu culoarea corectă de pe controler. Nu uita să testezi proiectul, asigurându-te că poți câștiga puncte și pierde vieți la momentul potrivit, și că jocul nu este prea ușor sau prea greu!

![screenshot](dots-all-test.png)

## Salvează proiectul { .save }

# Pasul 3: Mărește nivelul de dificultate { .activity .new-page}

Haide să facem jocul din ce în ce mai greu cu cât jucătorul supraviețuiește mai mult, prin reducerea graduală a intervalului dintre aparițiile a două puncte.

## Lista de activități { .check }

+ Creează o nouă variabilă numită `întârziere` {.blockdata} .

+ În scenă creează un script nou care setează `întârziere` la un număr mare și gradual o micșorează.

	```blocks
		when flag clicked
		set [delay v] to (8)
		repeat until < (delay) = (2)>
			wait (10) secs
			change [delay v] by (-0.5)
		end
	```

+ La final, poți să utilizezi această variabilă `întârziere` {.blockdata} in scripturile pentru punctele roșii, galbene și albastre. Înlocuiește codul care așteaptă un interval aleatoriu de timp între crearea clonelor și înlocuiește-l cu noua variabilă `întârziere` {.blockdata}:

	```blocks
		wait (delay) secs
	```

+ Verifică dacă intervalul de timp între crearea a două clone se micșorează în timp. Funcționează codul pentru toate cele 3 puncte colorate?

## Salvează proiectul { .save }

## Provocare: Puncte care se mișcă mai rapid {.challenge}
Poți să îmbunătățești jocul prin adăugarea unei variabile `viteză` {.blockdata} care controlează viteza, astfel încât punctele la început se deplasează câte un pas, și în mod constant încep să se miște din ce în ce mai repede? Este asemănător cu felul în care am utilizat mai sus variabila `întârziere` {.blockdata}.

## Salvează proiectul { .save }

# Pasul 4: Cel mai mare scor { .activity }

Haide să salvăm cel mai mare scor, astfel încât jucătorii să știe cât de buni sunt.

## Lista de activități { .check }

+ Creează o nouă variabilă numită `scor mare` {.blockdata}.

+ Click pe scenă și creează un nou bloc personalizat numit `verifică cel mai mare scor` {.blockmoreblocks} .

	![screenshot](dots-custom-1.png)

+ Chiar înainte de sfârșitul jocului adaugă noul bloc personalizat.

	![screenshot](dots-custom-2.png)

+ Adaugă cod la noul bloc pentru a păstra scorul curent `scor` {.blockdata} ca cel mai mare scor `scor mare` {.blockdata} dacă`if` {.blockcontrol} este cel mai mare scor de până acum:

	```blocks
		define [check high score]
		if <(score) > (high score)> then
			set [high score v] to (score)
		end
	```

+ Testează codul nou creat. Verifică dacă variabila `high score` {.blockdata} se modifică corect.

## Salvează proiectul { .save }

## Provocare: Îmbunătățește jocul! {.challenge}
Poți să te gândești la cum poți să îmbunătățești jocul? De exemplu, ai putea crea puncte special cu care poți să:

+ dublezi scorul;
+ încetinești coborârea punctelor;
+ ascunzi toate celelalte puncte de pe ecran!

## Salvează proiectul { .save }

## Provocare: Meniul jocului {.challenge}
Poți să adaugi la joc un meniu (cu butoane)? Ai putea adăuga un ecran cu instrucțiuni, sau un ecran separat pentru a arăta scorul cel mai mare. Dacă ai nevoie de ajutor, proiectul "Brain Game" îți poate fi de folos.

