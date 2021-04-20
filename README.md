<div dir="rtl" markdown="1">
	
# **פרוייקט SQL**

בפרוייקט אתם תבנו משחק טריוויה על מדינות העולם.

המשחק ימציא לבד שאלות על בסיס מאגרים ותבניות שאתם תבנו וילמד מהשחקנים איזה שאלות הן טובות ושכדאי לשמור ולשאול גם שחקנים אחרים.

לאחר כל שאלה השחקן יוכל לתת ציון לשאלה ובעזרת הדירוג המשחק ילמד האם כדאי לשאול את השאלה פעמים נוספות.

השחקן יפסל אחרי 3 תשובות לא נכונות ויקבל דירוג לפי כמות התשובות הנכונות עליהן ענה ולפי המהירות שענו על כל שאלה.

הניקוד ישמר ויוצגו השחקנים עם הניקוד הגבוה ביותר.

לפרוייקט תצטרכו להעזר בכל הכלים שלמדתם על בניית מאגרי נתונים וחילוץ מידע.

בפרוייקט עליכם להשתמש ב-MySQL כדי לשמור את כל המידע שמזין את המערכת. אין לשמור את המידע בכל צורה אחרת מלבד בסכמות ב-MySQL ויש לגשת למידע רק באמצעות שאילתות או שימוש ב-ORM.

בפרוייקט יש מספר תכולות שמוגדרות כבונוס	&#11088;, חלקן הן מימוש חלופי לתכולה וחלקן תכולות נוספות שהמשחק יכול להתקיים גם בלעדיהן.


הבונוס יכלל בציון וכדאי לבצע לפחות 2 בונוסים מהאופציות שינתנו.
   
   
<br/>

# בניית הסכמה

כדי לתכנן את המאגר בצורה המיטבית יש לקרוא את כל הנחיות הפרוייקט לפני התחלתה בנייה הסכמה.

מצורפים מספר קבצים המכילים מידע על מדינות העולם (כמו שטח, צפיפות, ערי בירה, מדד פשיעה, מדד יוקר מחיה ועוד).

עליכם לטעון את כל המידע הרלוונטי למאגר בצורה הגיונית כך שיהיה לכם נוח לבצע עליו שאילתות בהמשך.

שימו לב שייתכן שבחלק מהטבלאות שקיבלתם לא יופיעו כל המדינות.




<br/>

# ג'נרוט שאלות מתבניות

כדי לג'נרט שאלות מתוך המאגר שבנינו נצטרך להגדיר תבניות מסויימות שאליהן ניצוק את המידע.

סוגי תבניות השאלות:
### סוג 1 

שאלות שהתשובה עליהן היא שם של מדינה ואין משתנים בתוכן השאלה.
 
לכל שאלה מסוג זה יהיו 4 אופציות לתשובות.

לדוגמה: "באיזו מדינה חיים הכי הרבה אנשים?".

כל שאלה שתיווצר מתבנית זו תיהיה עם אופציות אחרות לתשובות ובכך תיצור כל פעם אתגר חדש.

האופציות השונות שינתנו מלבד התשובה הנכונה יהיו 

### סוג 2

שאלות עם משתנה בתוכן השאלה ושהתשובות לה הן פרמטרים ולא מדינות.

לכל שאלה מסוג זה יהיו 4 אופציות לתשובות.

לדוגמה: "מה עיר הבירה של מדינה X?"

השוני בין השאלות מתבנית זו הן במשתנה בתוכן השאלה ובאופציות שיוצגו כתשובות אפשריות.

כמובן שהאופציות שאינן התשובה הנכונה יהיו גם כן שייכות לאותו פרמטר של השאלה (בדוגמה שהצגנו האופציות הנוספות יהיו ערי בירה שגם כן נמצאות במאגר).

### &#11088; בונוס: סוג 3

שאלות המשוות בין שתי מדינות.

בשאלות אלה לכל שאלה יהיו שני משתנים בתבנית ושתי אופציות לתשובות - כן ולא.

לדוגמה: "האם לפי מדד יוקר המחיה יקר יותר לגור במדינה X מאשר מדינה Y?".

בתבנית זו השונה בין השאלות יהיה רק במשתנים (התשובות תמיד יהיו זהות - כן או לא).

המשתנים לגוף השאלה והאופציות לתשובות יבחרו רנדומלית ממאגר המדינות.

בסוף חלק זה המערכת צריכה ע"פ כל אחת מהתבניות לדעת ליצור שאלות ו-4 אופציות לתשובות הגיוניות כך שהמערכת גם תדע מה מבינהן היא האופציה הנכונה.

להלן רשימת התבניות, יש לממש את כולן (אם בחרתם בבונוס אז גם את כל התבניות מסוג 3).

עליכם להוסיף לפחות 4 תבניות נוספות משלכם על נתונים נוספים הקיימים במאגרים.

### Type 1:
* Which country is most populous? 
* Which country is least populous? 
* Which country is the largest by total area?
* Which country is the smallest by total area?
* Which country is the most densely populated? 
* Which country is the least densely populated? 
* Which country has the most cell phones per person?

### Type 2:
* What is the capital of X?
* How many people live in X?
* In what continent is X?

### Type 3:
* Are there more people in X than in Y?
* Is X larger than Y?
* Does X have a higher population density than Y? 
* Is the quality of life in X higher than the quality of life in Y?
* Is the crime rate of X higher than the crime rate in Y? 
* Are restaurants in X more expensive than restaurants in Y?

<br/>
         
# דירוג שאלות ושמירתן

בסוף כל שאלה תופיע לשחקן אופציה לדרג את השאלה בניקוד של 1 עד 5. השחקן לא יהיה חייב לדרג את השאלות.

הדירוג הזה נועד לעזור למערכת לדעת איזה מהשאלות שהיא יצרה הן טובות וכדאי לשמור אותן ולהמשיך להשתמש בהן מול שחקנם אחרים.

שאלה שנוצרה לראשונה תישמר רק אם היא קיבלה דירוג מהשחקן.

<br/>

## שיטת הדירוג לשאלה
בסוף כל שאלה יהיה לשחקן אופציה לתת דירוג לשאלה.

הדירוג יהיה 1-5 כאשר 1 זה הדירוג הנמוך ביותר.

מאחורי הקלעים ישמר הציון הממוצע של כל שאלה וכמות האנשים שנתנו דירוג לשאלה.

### מימוש בסיסי
משקל הדירוג של כל שחקן זהה.

אם במשחק הראשון שנשאלה שאלה מסויימת היא קיבלה דירוג 3, במשחק אחר היא קיבלה דירוג 5 ובמשחק נוסף דירוג 2 אז הציון של השאלה לאחר 3 המשחקים יהיה הממוצע של כל הדירוגים (כלומר 3.333).

### &#11088; מימוש בונוס 
משקל הדירוג של כל שחקן תלוי בניקוד הסופי שהשחקן יקבל בסוף המשחק (הסבר על הניקוד הסופי של השחקן ינתן בהמשך) כלומר, שחקן שנתן לשאלה מסויימת דירוג 3 והוא סיים את המשחק אחרי שהוא ענה נכון על 50 שאלות יחשב יותר מאשר שחקן שנתן לשאלה מסויימת דירוג 1 וענה נכון רק על 5 שאלות עד שנפסל. 
כך יחושב הדירוג:

> Score = [(Player A question rating) * (Player A final score) +... + (Player Y question rating)  (Player X final score)] / [(Player A final score) + ... + (Player Y final score)]

לדוגמה, אם שחקן A דירג 3 וסיים עם 200 נקודות, שחקן B דירג 5 וסיים עם 1000 נקודות ושחקן C דירג 2 וסיים עם 400 נקודות אז הדירוג הסופי יהיה:

(2 * 400 + 5 * 1000 + 3 * 200) / 1600 = 4


**דגשים:**
* הדירוג לשאלה יוכל להיות מחושב רק אחרי שהשחקן סיים את המשחק הנוכחי וקיבל את הניקוד הסופי
* כדי לחשב ולעדכן את דירוג השאלה צריך לשמור את כל התוצאות של השחקנים הקודמים והדירוג שהם נתנו לשאלה

<br/>

## מתי יוצגו שאלות שמורות ומתי יוצגו שאלות מג'ונרטות
בכל משחק יוצגו לשחקן שאלות שהמערכת יצרה באותו רגע וגם שאלות שמורות (שהמערכת יצרה במשחקים קודמים) וקיבלו דירוג גבוה.

### מימוש בסיסי
כל שאלה שלישית שתוצג לשחקן תיהיה שאלה שמורה.

### &#11088; מימוש בונוס 
בכל משחק לא תוצג לשחקן אותה שאלה שמורה פעמיים.

הסבירות להציג שאלה שמורה יחושב לפי הנוסחה הבאה:

N = כמות השאלות השמורות שלא נשאלו במשחק הספציפי

אם N=0 יוצגו רק שאלות שהמערכת יצרה באותו רגע

אם N * בין 0 ל-100 אז הסיכוי לקבל שאלה שמורה: 0.1 + 0.06N

אם N גדול מ-100 אז הסיכוי לקבל שאלה שמורה הוא 70%


כך למשל בהתחלת משחק ספציפי בו יש 30 שאלות שמורות אז הסיכוי בהתחלה לקבל שאלה שמורה יהיה 28% ולאחר שנשאלו 20 שאלות שמורות באותו משחק אז הסיכוי לקבל שאלה שמורה יהיה 16%.
  
<br/>

## איך תבחר שאלה ספציפית מתוך השאלות השמורות
נרצה שככל שגדל דירוג השאלה כך גם הסיכוי שהיא תופיע יעלה.

לכן נתייחס לדירוג השאלה כמשקל יחסי שבאמצעותו נחשב את הסבירות שתופיע כל שאלה.

Question chance = Question rating / All questions ratings combined

לדוגמה:

שאלה A - דירוג 5, שאלה B - דירוג 3, שאלה C - דירוג 1, שאלה D - דירוג 5, שאלה E - דירוג 2, שאלה F - דירוג 4.

סכום הדירוגים הוא 20 והסיכוי לכל שאלה:

A -> 5/20 = 25%; &nbsp;&nbsp;&nbsp;
B -> 3/20 = 15%; &nbsp;&nbsp;&nbsp;
C -> 1/20 = 5%;&nbsp;&nbsp;&nbsp;
D -> 5/20 = 25%;&nbsp;&nbsp;&nbsp;
E -> 2/20 = 10%;&nbsp;&nbsp;&nbsp;
F -> 4/20 = 20%

שימו לב שאם בחרתם במימוש הבונוס בסעיף הקודם צריך להתחשב בכך שאחרי כל שאלה מספר האופציות לשאלות מצטמצם ויש לחשב מחדש את הסיכוי של כל שאלה.

<br/>

# מהלך המשחק
בתחילת המשחק השחקן יצטרך להזין את שמו כך שבסוף המשחק השם ישמר בלוח התוצאות (אין צורך לממש יוזרים או לבצע אותנטיקציה).\

לשחקן תוצג כל פעם שאלה מג'ונרטת או שאלה שמורה (כפי שהוסבר לעיל) שעליה הוא יקבל אינדיקציה אם הוא צדק או טעה ולאחר מכן תיהיה לו האופציה לדרג את השאלה.

השאלות יוג'נרטו בלייב תוך כדי המשחק.
  
<br/>

## חישוב הניקוד לכל שאלה

לשחקן יוצג לאורך כל המשחק הניקוד הנוכחי שלו וכמה נקודות הוא קיבל על כל תשובה נכונה.

### מימוש בסיסי
על כל שאלה נכונה השחקן מקבל 100 נקודות. אם השחקן טעה הוא לא מקבל נקודות.

אחרי 3 תשובות לא נכונות מסתיים המשחק.

### &#11088; מימוש בונוס 
המענה על שאלה מוגבל בזמן, בהתחלה לשחקן יש 20 שניות לענות על שאלה ובכל שאלה נכונה הזמן יורד בחצי שניה עד שהוא מגיע למינימום של 5 שניות לשאלה.

הזמן שנותר יוצג לשחקן.

אם השחקן לא ענה במסגרת הזמן הוא יקבל פסילה על השאלה ויעבור לשאלה הבאה.

הניקוד יחושב לפי הזמן שלקח לשחקן לענות על השאלה בצורה הבאה:

> Score = (1 - Time it took to answer / Total time given) * 70 + 30
 
כך לדוגמה אם לשאלה מסויימת ניתנו 15 שניות לענות והשחקן ענה תוך 10 שניות אז הניקוד שהוא יקבל על השאלה יהיה 53.333.

  
<br/>

## לוח תוצאות
לפני התחלת המשחק לשחקן תיהיה האופציה לראות את לוח התוצאות.

לוח התוצאות מכיל את שמות כל השחקנים ששיחקו ואת הניקוד שקיבלו בסדר יורד.

בסוף כל משחק יוצג לשחקן הניקוד הסופי ואת המקום שלו בדירוג.

<br/>

# תכולות נוספות למשחק
כל התכולות המובאות כאן הן בונוסים שלא תלויים ישירות במימוש שכבר בניתם למשחק.
  
<br/>

## &#11088; בונוס: הצגת הנתונים לשחקן אחרי כל תשובה
בסוף כל שאלה יוצגו לשחקן הנתונים הרלוונטים לכל אחת מהאופציות.

לכל סוג תבנית יוצגו נתונים אחרים.

**נסביר באמצעות דוגמאות**

בתבניות מסוג 1:

בשאלה: Which country is most populous? 

יופיעו 4 אופציות: סין, ישראל, ארה"ב וקנדה.

לאחר שהשחקן יבחר באחת האופציות תוצג לצד כל אופציה את כמות התושבים שחיים באותה מדינה.

בתבניות מסוג 2:

בשאלה: What is the capital of Japan?

יופיעו 4 אופציות: ירושלים, טוקיו, מוסקבה ומקסיקו סיטי.

לאחר שהשחקן יבחר באחת האופציות תוצג לצד כל אופציה המדינה אליה שייכת אותה האופציה.

בתבניות מסוג 3:

בשאלה: Is the crime rate of Canada higher than the crime rate in Costa Rica? 

לאחר שהשחקן יבחר באחת האופציות יוצג מה רמת הפשיעה בכל מדינה.
  
<br/>

## &#11088; בונוס: טיוב האופציות בשאלות
במימוש הנוכחי האופציות הניתנות לשאלות הן רנדומליות, נרצה לשנות את זה כך שחלק מהאופציות יהיו קרובות לתשובה וכך יגרמו לשאלה להיות קשה יותר.

**נסביר באמצעות דוגמאות**

בתבניות מסוג 1:

בשאלה: Which country is most populous? 

יופיעו 4 אופציות: ברזיל, פקיסטן, ספרד וישראל

למה דווקא האופציות האלה? כי בברזיל חיים 188 מיליון איש ובפקיסטן 165 מיליון (מקום 5 ו-6 בעולם) ושאר האופציות רחוקות יותר.

בתבניות מסוג 3:

בשאלה: Is the quality of life in Estonia higher than the quality of life in Sweden? 

הסיבה שנבחרו דווקא שוודיה ואסטוניה היא כי מדד איכות החיים שלהן מאוד קרוב (177.82 לאסטוניה ו-175.92 לשוודיה - מקומות 10 ו-11 בעולם).

לא רלוונטי לממש את ההגיון לתבניות מסוג 2.
  
<br/>

## &#11088; בונוס: גלגל הצלה לשאלות
בכל שלב לשחקן יהיה אופציה להשתמש בגלגל הצלה - מצמצם לו את 4 האפשרויות ל-2 אפשרויות ומוסיף לו 10 שניות לענות על השאלה (במידה ומימשתם טיימר לשאלות).

לשחקן יש 2 גלגלי הצלה במשחק.

שאלות שעליהן ענה השחקן עם גלגל הצלה יקנו לו אוטומטית רק 30 נקודות במקום מלוא הנקודות.

לתבניות מסוג 3 לא יתאפשר להפעיל גלגל הצלה.

__בהצלחה!__
</div>
