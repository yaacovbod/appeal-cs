# שאלון ערעור על ציון הגשה — מדעי המחשב

## מטרת הפרויקט
טופס ערעור לתלמידים המבקשים לשנות ציון הגשה במדעי המחשב.

## טכנולוגיות
- הקובץ `index.html` — טופס חד-שלבי, HTML סטטי, Vanilla JS
- הקובץ `dashboard.html` — דשבורד עם Chart.js, טעינת נתונים דרך JSONP
- שימוש ב-Apps Script המרכזי המשותף לכל שאלוני המשוב

## Apps Script — פרטים טכניים
- כתובת ה-URL: `https://script.google.com/macros/s/AKfycbyFDlBHn07-bzcBGhok5pVsrFsQcvwspYEf8DF8toXFzog-qhkerIbNc361-Xij3W2VAg/exec`
- שאלון זה שולח `sheetName: 'ערעור מדעי המחשב'` — נתונים נשמרים בגיליון "ערעור מדעי המחשב"
- שיטת שליחה: hidden iframe POST
- שיטת קריאה לדשבורד: JSONP עם פרמטר `callback` ו-`sheetName`

## עיצוב
- סגנון Clarity: לבן, טורקיז (#0891B2), פונט Heebo
- מינימליסטי ונקי

## קהל יעד
תלמידים הרוצים לערער על ציון הגשה במדעי המחשב

## מבנה הנתונים ב-Google Sheets (גיליון "ערעור מדעי המחשב")
עמודות: חותמת זמן, שם מלא, ציון קיים, ציון מבוקש, סיבה לבקשה

## קבוצות לימוד
קבוצה אחת בלבד במקצוע — אין שדה בחירת קבוצה בטופס

## עדכון נדרש ב-Apps Script
יש להוסיף לקובץ `feedback/גדנע/apps-script.js` את הקונפיגורציה הבאה ב-SHEETS_CONFIG:
```js
'ערעור מדעי המחשב': {
  headers: ['חותמת זמן','שם מלא','ציון קיים','ציון מבוקש','סיבה לבקשה'],
  fields:  ['timestamp','fullName','currentGrade','requestedGrade','reason']
}
```
לאחר העדכון יש לפרוס מחדש (New deployment) ב-Google Apps Script.
