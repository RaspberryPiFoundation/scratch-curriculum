---
title: נאבד בחלל
level: Scratch 1
language: he-IL
stylesheet: scratch
embeds: "*.png"
materials: ["Club Leader Resources/*"]
...

# מבוא { .intro }

בפרויקט זה נלמד איך לבנות את האנימציה משלנו

<div class="scratch-preview">
  <iframe allowtransparency="true" width="485" height="402" src="http://scratch.mit.edu/projects/embed/26818098/?autostart=false" frameborder="0"></iframe>
  <img src="space-final.png">
</div>

# שלב 1: אנימציה של חללית { .activity .new-page}

בואו נגרום לחללית לטוס לכיוון של כדור הארץ

## סדר פעולות { .check }

+ נתחיל פרויקט חדש ונמחק את החתןל
<a href="http://jumpto.cc/scratch-new">jumpto.cc/scratch-new</a>

+ נוסיף 2 דמויות: חללית וכדור הארץ ורקע עם כוכבים. הפרויקט אמור להראות ככה

	![screenshot](space-sprites.png)

+ נלחץ על חללית ואז על תלבושות

	![screenshot](space-costume.png)

+ נשתמש בחץ כדי לבחור את התמונה ואז נלחץ על עיגול מעל התמונה כדי לסובב אותה הצידה
	
	![screenshot](space-rotate.png)

+ נוסיף קוד לדמות

	![screenshot](space-animate.png)

	נשנה את המספרים בתוך הבלוק כדי שהם יהיו זהים לאלו שבתמונה

+ נלחץ ונבקוד אם החללית זזה לכיוון המרכז

	![screenshot](space-animate-stage.png)
	
	חשוב להכיר את מיקום הדמויות על הבמה. אם איקס ו-וואי שלישיים הדמות תהיה בפינה שמאלית תחתונה ואם הערכים חיוביים הדמות תהיה בפינה ימנית עליונה

	![screenshot](space-xy.png)

	אם אנחנו לא בטוחים לגבי המיקום תמיד אפשר לבדוק אותו במעבר העכבר על הבמה - בפינה ימנית תחתונה נראה את הקואורדינטות של העכבר

	![screenshot](space-coordinates.png)

+ נלחץ על הדגל הירוק לבדוק את האנימציה

	![screenshot](space-flag.png)

## אתגר: שדרוג אנימציה {.challenge}
אפשר לשנות מספרים באנימציה 
+ אם החללית נוגעת בכדור הארץ
+ אם חללית זזה מהר מידי

אפשר לשחק עם המספרים בבלוק זה

  ![screenshot](space-glide.png)

## נשמור את הפרויקט { .save }

# שלב 2: אנימציה דרך לולאות { .activity .new-page }

דרך נוספת להוסיף אנימציה היא בהוספת תנועה קטנה הרבה פעמים

## סדר פעולות { .check }

+ נמחק בלוק גלישה בלחיצה על כפתור ימני ובחירה במחק. אם למחוק את בלוקים בעזרת לגרירה לאיזור של תסריטים

	![screenshot](space-delete-glide.png)

+ נוסיף קוד חדש של לולאה

	![screenshot](space-loop.png)

	בלוק חזור...פעמים משמש לחזרה על פעולה מסויימת הרבה פעמים - ידוע גם כלולאה

+ נלחץ על הדגל ונבדוק את הקוד

+ אפשר לשדרג את הלולאה בהוספה של שינוי צבע מתוך מראה

	![screenshot](space-colour.png)

+ נלחץ על הדגל ונבדוק את הקוד

	![screenshot](space-colour-test.png)

+ ועכשיו נוסיף שינוי גודל של חללית בדרך שלה לכדור הארץ

	![screenshot](space-size.png)

+ נלחץ כמה פעמים על הדגל. החללית הפכה לקטנה מידי? זה הזמן להחזיר לה את הגודל המקורי

	![screenshot](space-size-100.png)

## נשמור את הפרויקט { .save }

# שלב 3: סיבוב של הקוף { .activity .new-page }

בואו נוסיף אנימציה לקוף שנאבד בחלל

## סדר פעולות { .check }

+ נוסיף דמות של הקוף

	![screenshot](space-monkey.png)

+ ניכנס לתלבושות ונערוך איך הקוף נראה. נלחץ על אליפסה ונוסיף עיגול סביב ראש הקוף

	![screenshot](space-monkey-edit.png)

+ נחזור לתסריטים ונגרום לקוף להסתובב סביב עצמו לעולמים

	![screenshot](space-monkey-move.png)

	לעולמים זו לולאה שפועלת ללא הפסקה עד סיום ההרצה

+ נחלץ על הדגל כדי לבדוק את האנימציה. עצירה של אנימציה זו אפשרית בלחיצה על עצור

	![screenshot](space-monkey-loop.png)

# שלב 4: התנגשות אסטרואידים { .activity .new-page }

ועכשיו נתקדם לאנימציה של התנגשות

## סדר פעולות { .check }

+ נוסיף אסטרואיד לבמה

	![screenshot](space-rock-sprite.png)

+ ועכשיו הקוד של אסטרואיד

	![screenshot](space-brick-loop.png)

+ נלחץ על הדגל כדי לבדוק את הקוד. האם החללית מתנגשת בקצוות של הבמה

# שלב 5: כוכבים { .activity .new-page }

ועכשיו נחבר כמה לולאות ביחד וניצור אנימציה לכוכבים

## סדר פעולות { .check }

+ נוסיף כוכב לבמה

	![screenshot](space-star-sprite.png)

+ נוסיף קוד לכוכב

	![screenshot](space-star-move.png)

+ נלחץ על הדגל כדי לבדוק את הקוד. מה הכוכב עושה? הוא גדל באיטיות ואז קטן באיטיות ועושה זאת כל הזמן

## נשמור את הפרויקט { .save }

## אתגר: תעשה אנימציה משלך {.challenge}
תעצור את האנימציה ותשמור את הפרויקט

השתמש במה שלמדת כדי ליצור אנימציה שלך

![screenshot](space-egs.png)

## נשמור את הפרויקט { .save }
