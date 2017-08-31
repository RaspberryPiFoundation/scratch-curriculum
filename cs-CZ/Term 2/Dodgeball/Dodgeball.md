---
title: Dodgeball
level: Scratch 2
language: cs-CZ
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*","Project Resources/*"]
...

# Úvod { .intro }

V tomto projektu se naučíš jak vytvořit plošinovku, kde se musíš vyhnout pohybujicí se kouli a dostat se až na konec levelu.

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/39740618/?autostart=false" frameborder="0"></iframe>
  <img src="dodge-final.png">
</div>

# Krok 1: Pohyb postavy { .activity }

Nejdřiv vytvoříme postavu která se může pohybovat doleva a doprava, a taky šplhat po tyčích.

## Postup { .check }

+ Vytvoř nový projekt ve Scratchi a smaž kočičí sprite tak, aby byl projekt prázndý. Webový scratch editor najdeš na <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>.
+ Pro tento projekt bys měl mít složku 'Project Resources', kde bude obrázek s pozadím, který budeš chtít. Přesvědč si že víš kde ta složka je, a pokud ne zeptej se tvého vedoucího týmu.

	![screenshot](dodge-resources.png)

+ Přidej obrázek 'background.png' jako nový pozadí scény, nebo si nakresli vlastní! Pokud budeš kreslit vlastní úroveň, ujisti se ze tyče a podlahy mají jiné barvy, a že tam jsou dveře (nebo něco jiného) kam musíš se svou postavičkou dojít. Takhle nějak by měl tvůj obrázek vypadat:

	![screenshot](dodge-background.png)

+ Přidej nový sprite, který bude tvou postavou. Vyber si raději sprite s více kostýmy, aby jsi mohl udělat jako že postava chodí.

	![screenshot](dodge-characters.png)

+  Budeme používat šípky aby jsi pohyboval postavou. Když hráč zmáčkne pravou šipku, chceš aby tvoje postava se otočila doprava, udělala několik kroků a vyměnila do dalšího kostýmu:

	```blocks
		when flag clicked
		forever
			if <key [right arrow v] pressed? > then
				point in direction (90 v)
				move (3) steps
				next costume
			end
		end
	```
+ Vyzkoušej pohyb své postavy kliknutím na tyčku a pak podržením šipky doprava. Hýbe se tvoje postava doprava? Vypadá tvoje postava jako že chodí?

	![screenshot](dodge-walking.png)

+ Na pohyb postavy doleva, budeme potřebovat další `když` {.blockcontrol} blok uvnitř tvého cyklu `opakuj stále` {.blockcontrol}, který bude hýbat postavou doleva. Nezapomeň vyzkoušet svůj nový kód, aby jsi ujistil že funguje! Pokud se tvoje postava otočí vzhůru nohama ve chvíli, když chodí doleva, přidej blok `nastav způsob otáčení` {.blockcontrol} nad blokem `opakuj stále` {.blockcontrol}:

	```blocks
		when flag clicked
		set rotation style [left-right v]
		forever
			if <key [right arrow v] pressed? > then
				point in direction (90 v)
				move (3) steps
				next costume
			end
		end
	```

+ Na šplhání po tyčí, tvoje postava se musí pohnout maličko nahoru když je zmáčknuta šipka nahoru a postava se dokýká správné barvy. Přidej tento kód dovnitř bloku `opakuj stále` {.blockcontrol}:

	```blocks
		if < <key [up arrow v] pressed?> and <touching color [#FFFF00]?> > then
			change y by (4)
		end
	```
+ Vyzkoušej svojí postavu - můžeš vyšplhat po žlutých tyčích a dostat se na konec úrovně?

	![screenshot](dodge-test-character.png)

## Ulož svůj projekt { .save }

## Výzva: Dokončení úrovně {.challenge}
Dokážeš přidat kód ke tvé postavy, aby nečo řekla `když` {.blockcontrol} se dostane ke hnědým dveřím?

![screenshot](dodge-win.png)

## Ulož svůj projekt { .save }

# Krok 2: Přitažlivost a skákání { .activity }

Uděláme pohyb postavy vice reální, když přidáme přitažlivost a umožníme postavě skákat.

## Postup { .check }

+ Možná sis všiml že tvoje postava může chodit i mimo podlah a zůstat ve vzduchu. Zkus vyjít stranou z podlahy a pozoruj co se stane.

	![screenshot](dodge-no-gravity.png)

+ Aby jsme toto napravili, přidáme do hry přitažlivost. Vytvoř novou proměnnou nazvanou `gravitace` {.blockdata}. Můžeš tuto proměnnou schovt ze scény, pokud budeš chtít.

	![screenshot](dodge-gravity.png)

+ Přidej tento nový blok kódu, který nastaví gravitace na zápornou hodnotu, a pak použije tuto na změnu y-pozice tvé postavy.

	```blocks
		when flag clicked
		set [gravity v] to [-4]
		forever
			change y by (gravity)
		end
	```

+ Klikni na vlajku, a pak přetáhni svou postavu na vršek tvé scény. Co se stane? Funguje přitažlivost jak jsi očekával?

	![screenshot](dodge-gravity-drag.png)

+ Přitažlivost by neměla hýbat postavou skrz podlahu nebo tyč! Přidej blok `jestli` {.blockcontrol} do tvého kódu, aby přitažlivost fungovala jen pokud bude postava ve vzduchu. Kód pro přitažlivost by měl vypadat asi takto:

	```blocks
		when flag clicked
		set [gravity v] to [-4]
		forever
			if < not < <touching color [#0000FF]?> or <touching color [#FFFF00]?> > > then
				change y by (gravity)
			end
		end
	```

+ Vyzkoušej přitažlivost znovu. Zastaví se pád postavy když stoji na podlaze nebo se drží tyče? Můžeš spadnout z kraje podlahy a dopadnout na podlahu níže?

	![screenshot](dodge-gravity-test.png)

+ Pojďme taky zařídit aby postava skočila když hráč zmáčkne mezerník. Velmi jednoduchý způsob jak toto zařídit je pohnout postavou nahoru nekolikrát, pomocí tohoto kódu:

	```blocks
		when [space v] key pressed
		repeat (10)
			change y by (4)
		end
	```

  Protože přitažlivost stále tlačí postavu dolů o 4 pixelů, musíš zvolit číslo větší než 4 ve tvém bloku `změn y o (4)` {.blockmotion}. Změň toto čislo tak aby jsi byl spokojený s tím, jak tvoje postava skáče.

+ Až budeš tento kód zkoušet, všimni si že pohyb postavy není moc plynulý. Aby bylo skákání plynulejší, budeš muset hýbat postavou o čím dále mensí počet pixelů, dokud se její pohyb nahoru zastaví.

+ Na to vytvoříme další proměnnou `výška skoku` {.blockdata}. Můžeš tuto proměnnou opět schovat, pokud budeš chtít.

+ Smaž kód skákání který jsme přidali k postavě, a nahraď tímto kódem:

	```blocks
		when [space v] key pressed
		set [jump height v] to [8]
		repeat until < (jump height) = [0] >
			change y by (jump height)
			change [jump height v] by (-0.5)
		end
	```

  Tento kód hýbe postavou o 8 pixelů, poté o 7,5 pixelů, poté 7 pixelů a tak dále, dokud postava neskončí skok. Toto pomůže aby byly skoky o hodně plynulejší.

+ Změň počáteční hodnotu tvé proměnné `výška skoku` {.blockdata} a vyzkoušej program tak, aby jsi byl spokojen s výškou skoku tvé postavy.

## Ulož svůj projekt { .save }

## Výzva: vylepšené skákání {.challenge}
Tvoje postava může skočit kdykoliv je zmáčknutý mezerník, i když je postavička ve vzduchu. Můžeš toto vyzkoušet podržením mezerníku. Můžes toto opravit tak aby postava mohla skočit pouze `jestli` {.blockcontrol} se dotýká modré podlahy?

## Ulož svůj projekt { .save }

# Step 3: Dodging balls { .activity .new-page}

Now that you've got your character moving around, let's add some balls for your character to avoid.

## Activity Checklist { .check }

+ Create a new ball sprite. You can choose any type of ball you like.

	![screenshot](dodge-balls.png)

+ Resize your ball, so that your character can jump over it. Try jumping over the ball to test it.

	![screenshot](dodge-ball-resize.png)

+ Add this code to your ball:

	![screenshot](dodge-ball-motion.png)

	This code creates a new ball clone every 3 seconds. Each new clone moves along the top platform.

+ Click the flag to test this out.

	![screenshot](dodge-ball-test.png)

+ Add more code to your ball sprite, so that they move across all 3 platforms.

	![screenshot](dodge-ball-more-motion.png)

+ Finally, you'll need code for when your character gets hit by a ball! Add this code to your ball sprite:

	```blocks
		when I start as a clone
		forever
			if < touching [Pico walking v]? > then
				broadcast [hit v]
			end
		end
	```

+ You'll also need to add code to your character, to move back to the start when they're hit:

	```blocks
		when I receive [hit v]
		point in direction (90 v)
		go to x: (-210) y: (-120)
	```

+ Test out your character and see if they go back to the start when they've been hit by a ball.

## Save your project { .save }

## Challenge: Random balls {.challenge}
The balls your character has to dodge all look the same, and always appear every 3 seconds. Can you improve them, so that they:

+ don't all look the same?
+ appear after a random amount of time?
+ are a random size?

![screenshot](dodge-ball-random.png)

## Save your project { .save }

# Step 4: Lasers! { .activity .new-page}

Let's make your game a little harder to complete, by adding lasers!

## Activity Checklist { .check }

+ Add a new sprite to your game, called 'Laser'. It should have 2 costumes, called 'on' and 'off'.

	![screenshot](dodge-lasers-costume.png)

+ Place your new laser anywhere you like, between 2 platforms.

	![screenshot](dodge-lasers-position.png)

+ Add code to your laser, to make it switch between the 2 costumes.

	```blocks
		when flag clicked
		forever
			switch costume to [on v]
			wait (2) secs
			switch costume to [off v]
			wait (2) secs
		end
	```

	If you prefer, you can `wait` {.blockcontrol} a `random` {.blockoperators} amount of time between costume changes.

+ Finally, add code to your laser, so that the 'hit' message is broadcast when the laser touches your character. This code will be the same as the code you added to your ball sprite.

	You don't need to add any more code to your character - they already know what to do when they get hit!

+ Test out your game to see if you can get past the laser. Change the `wait` {.blockcontrol} times in your code if the lasers are too easy or too hard.

## Challenge: More obstacles {.challenge}
If you think your game is still too easy, you can add more obstacles to your level. You can add anything you like, but here are some ideas:

+ A flying killer butterfly;
+ Platforms that appear and disappear;
+ Falling tennis balls that must be avoided.

![screenshot](dodge-obstacles.png)

You could even create more than one backdrop, and move to the next level when your character reaches the brown door:

```blocks
	if <touching color [#714300]?> then
		switch backdrop to [next backdrop v]
		go to x: (-210) y: (-120)
		wait (1) secs
	end
```

## Save your project { .save }

## Challenge: Improved gravity {.challenge}
There's one other small bug in your game: gravity doesn't pull your character downwards if _any_ part of it is touching a blue platform - even its head! You can test this out by climbing most of the way up a pole and then moving to the left.

![screenshot](dodge-gravity-bug.png)

Can you fix this bug? To do this, you need to give your character different coloured trousers (on _all_ costumes)...

![screenshot](dodge-trousers.png)

...and then replace the code:

```blocks
	< touching color [#0000FF]? >
```

with:

```blocks
	< color [#00FF00] is touching [#0000FF]? >
```

Remember to test your improvements to make sure you've fixed the bug!

## Save your project { .save }

## Challenge: More lives {.challenge}
Can you give your player 3 `lives` {.blockdata}, instead of just sending them back to the beginning each time? Here's how your game could work:

+ Your player starts with 3 lives;
+ Whenever your player gets hit, one life is lost and they go back to the start;
+ If there are no lives left, the game ends.

## Save your project { .save }
