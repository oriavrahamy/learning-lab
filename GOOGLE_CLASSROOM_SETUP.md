# מדריך מהיר: חיבור Google Classroom לאפליקציה (צעד אחר צעד)

המטרה: להוסיף באפליקציה לשונית `Google Classroom` עם התחברות גוגל נפרדת.

## מה תעשה עכשיו (בלי קוד)

1. היכנס ל-Google Cloud Console  
   קישור: https://console.cloud.google.com/

2. צור פרויקט חדש (או בחר פרויקט קיים)  
   מומלץ שם ברור, לדוגמה: `learning-lab-classroom`.

3. הפעל את Google Classroom API  
   1. בתפריט: `APIs & Services` -> `Library`  
   2. חפש `Google Classroom API`  
   3. לחץ `Enable`

4. הגדר מסך הרשאות OAuth (פעם ראשונה בלבד)  
   1. בתפריט: `APIs & Services` -> `OAuth consent screen`  
   2. בחר סוג משתמש:
      - `External` אם זה חשבון Gmail רגיל
      - `Internal` אם זה ארגון Google Workspace
   3. מלא App name + email
   4. שמור

5. הוסף משתמשי בדיקה (אם האפליקציה ב-Testing)  
   במסך OAuth, תחת `Test users`, הוסף את כתובת ה-Gmail שלך.

6. צור OAuth Client ID נפרד ל-Classroom  
   1. בתפריט: `APIs & Services` -> `Credentials`  
   2. `Create Credentials` -> `OAuth client ID`  
   3. בחר `Web application`
   4. תן שם, לדוגמה: `classroom-web-client`

7. הגדר Authorized JavaScript origins  
   הוסף את כל המקורות שמהם אתה מריץ את האפליקציה, לדוגמה:
   - `http://localhost:3000`
   - `http://127.0.0.1:5500`
   - או הדומיין האמיתי שלך בפרודקשן

8. העתק את ה-Client ID שנוצר  
   הוא נראה בערך כך:  
   `1234567890-abcxyz.apps.googleusercontent.com`

## מה לשלוח לי כדי שאשלים את הקוד

שלח לי:

1. `Classroom Client ID` שיצרת
2. מאיזה URL אתה מריץ את האפליקציה (למשל `http://127.0.0.1:5500`)

## מה אני אעשה אחרי שתשלח

אני אבצע בשבילך:

1. הוספת לשונית חדשה: `Google Classroom`
2. הוספת חיבור גוגל נפרד ל-Classroom
3. התחברות עם בחירת חשבון (כדי לאפשר חשבון אחר מהחיבור הקיים)
4. משיכת קורסים/מטלות מ-Classroom והצגה במסך
5. מסך הגדרות לשמירת `Classroom Client ID` בנפרד

## בדיקת תקינות מהירה (אחרי שאסיים קוד)

1. פותחים את הלשונית `Google Classroom`
2. לוחצים התחבר
3. בוחרים חשבון גוגל
4. מאשרים הרשאות
5. רואים רשימת קורסים/משימות

## תקלות נפוצות

1. `origin_mismatch`  
   ה-URL שבו אתה מריץ לא מופיע ב-Authorized JavaScript origins.

2. `access blocked / app not verified`  
   לרוב זה בגלל OAuth consent screen לא מלא או משתמש שלא נוסף ל-Test users.

3. אין נתונים ב-Classroom  
   התחברת לחשבון שאין בו קורסים/מטלות.

