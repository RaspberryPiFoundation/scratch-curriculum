---
title: להקת רוק
level: Scratch 1
language: he-IL
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

# מבוא { .intro }

בפרויקט זה תלמדו איך ליצור את כלי נגינה שלכם!

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26741186/?autostart=false" frameborder="0"></iframe>
  <img src="band-final.png">
</div>

# שלב 1: דמויות { .activity }

לפני שנתחיל להפעיל אנימציה, בואו נבחר דמות. 

## סדר פעולות { .check }

+ קודם כל נפתח אורך סקראצ' <a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>. זה נראה ככה:

	![screenshot](band-scratch.png)

+ עכשיו נמחק את החתול : לחיצה ימנית על העכבר – בחירת אפשרות "מחק".

	![screenshot](band-delete.png)

+ עכשיו נבחר דמות של כלי גנינה מתוך המאגר.

	![screenshot](band-sprite-library.png)

+ נמצא את התופים ונלחץ פעמיים על הדמות כדי שהיא תתווסף לפרויקט.

	![screenshot](band-sprite-drum.png)

+ נקטין את הדמות כדי שהיא תתאים למשחק

	![screenshot](band-shrink.png)

## שמור את הפרויקט { .save }
לא  נשכח לשנות את שם הפרויקט בפינה שמאלית עליונה

הפרויקט נשמר אוטומטית, אך ליתר הבטחון נכנס ל"קובץ" ונבחר שמור עכשיו

![screenshot](band-save.png)

# Step 2: הבמה { .activity }

במה זה איזור בוא אנו רואים את כל הפרויקט, בדיוק כמו במה אמיתית.

## סדר פעולות { .check }

+ בהתחלה הבמה עם רקע לבן וזה די משעמם. בואו נבחר רקע חדש. 
נלחץ על בחר רקע מהסיפרייה


	![screenshot](band-stage-choose.png)

+ נבחר את הרקע בלחיצה כפולה עליו.

	![screenshot](band-backdrop.png)

+ עכשיו הבמה שלנו תראה ככה:

	![screenshot](band-stage.png)

# Step 3: נפעיל את התופים { .activity }

עכשיו נגרום לתוף להשמיע צליל.

## סדר פעולות { .check }

+ נוודא שאנו נמצאים בלשונית תסריטים (Scripts). כל התסריטים צבועים בצבעים שונים. 

	נבחר באירועים (Events) ומצא את הבלוק "כאשר לוחצים על הדמות" (when this sprite clicked), נגרור אותו לאיזור אפור בצד ימין  ואז נעבור לצלילים (Sounds) ונבחר נגן תוף ... (play drum () for () beats) וגם אותו נגרור. חשוב לוודא ששני הבלוקים מחוברים. 	

	![screenshot](band-code.png)

+ נלחץ על התופים וננסה אותם!

+ אפשר גם לשנות את התלבושת של בתוף בלחיצה עליו. לשם כך נעבור לתלבושות.

	![screenshot](band-drum-costume.png)

+ כדי ליצור תלבושת חדשה – נלחץ כפתור ימני על העכבר – ונבחר "העתק".

	![screenshot](band-drum-duplicate.png)

+ נעכשיו נבחר בתלבושת שנוצרה ונצייר עליה קוים.

	![screenshot](band-drum-hit.png)

+ כדאי גם שנשנה את השמות כדי שיהיה לנו קל לנהל אותם בהמשך.

	![screenshot](band-drum-name.png)

+ עכשיו כאשר יש לנו 2 תלבושות, נבחר איזו נציג במצב רגיל ואיזה במצב לחיץ

	![screenshot](band-looks.png)
עכשיו נוכל להחליף בין התלבושות. נחזור לתסריטים (Scripts) ונבחר ב {.blocklooks} . שם נבחר החלף תלבושת ל... ונשים לפני נגן תלובשת אחד ואחרי – תלבושת אחרת. כמו קודם – הכל בגרירה לצד ימין וחיבור בין הבלוקים.


+ נלחץ על התוף ונבוודא שהקוד פועל

## נשמור את הפרויקט { .save }

##אתגר : נשדרג את התופים { .challenge }

+ האם תוכל לשנות את הצליל של התוף בלחיצה עליו?

![screenshot](band-drum-sound.png)

+ האם תוכל להפעיל את הפוף בלחיצה על המקלדת {.blockevents} :

```blocks
	when [space v] key pressed
```

ניתן לשכפל את הקוד בלחיצה ימנית עליו ואז "העתק"

![screenshot](band-duplicate-code.png)

## נשמור את הפרויקט { .save }

# שלב 4 : זמרת { .activity .new-page }

בואו נוסיף זמרת ללהקה

## סדר פעולות { .check }

+ נוסיף עוד 2 דמויות זמרת ומיקרופון.

	![screenshot](band-singer-mic.png)

+ לפני שנתחיל לעשות את הזמרת, בואו נוסיף צלילים לדמות. חשוב לוודא שאנו בדמות הנכונה (דמות שמסומנת בפינה שמאלית תחתונה). ואז נלחץ על לשונית צלילים (Sounds).

	![screenshot](band-import-sound.png)

+ נבחר את הצליל מהמאגר ובלחיצה כפולה על העכבר נוסיף לרשימה.

	![screenshot](band-choose-sound.png)

+ כאשר הצליל התווסף, נפעיל את הקוד. נעבור חזרה לתסריטים(Scripts). באירועים (Events) נבחר “כאשר לוחצים על הדמות” (when this sprite clicked) ואז בצלילים שבתוך התסריטים נבחר “נגן צליל [] עד שמסתיים” (play sound [singer1 v] until done). 

	```blocks
		when this sprite clicked
		play sound [singer1 v] until done
	```

+ נלחץ על הזמרת ונוודא שהכל עובד.

## נשמור את הפרויקט { .save }

##אתגר: שינוי תלבושת לזמרת { .challenge }
האם תוכל לשנות את המראה של הזמרת כאשר לוחצים עליה? 

![screenshot](band-singer-final.png)

לא לשכוח לבדוק שהקוד החדש עובד!

## נשמור את הפרויקט { .save }

##אתגר: תנסה ליצור להקה שלמה { .challenge }
השתמש בכל מה שלמדת כדי ליצור להקה משלך. השתמש בכלי נגינה שיש במאגר או תיצור משלך, תוסיף צלילים

![screenshot](band-ideas.png)

כמה רעיונות בשבילך

![screenshot](band-piano.png)

צייר חדשים גם

![screenshot](band-draw.png)

ואף הקליד צלילים משלך אם יש לך מירקופון במחשב

![screenshot](band-io.png)

## שמור את הפרויקט { .save }
