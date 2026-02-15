# 🔥 Firebase Setup Guide

Denne guide hjælper dig med at opsætte Firebase Realtime Database til global highscore funktionalitet.

## 📋 Trin-for-Trin Instruktioner

### 1. Opret Firebase Projekt

1. Gå til [Firebase Console](https://console.firebase.google.com/)
2. Klik på **"Add project"** eller **"Tilføj projekt"**
3. Indtast et projektnavn (f.eks. "flappy-eagle")
4. Valgfrit: Deaktiver Google Analytics (ikke nødvendigt for dette projekt)
5. Klik **"Create project"**

### 2. Aktiver Realtime Database

1. I Firebase Console, vælg dit projekt
2. Klik på **"Realtime Database"** i venstre menu (under "Build")
3. Klik **"Create Database"**
4. Vælg en location (f.eks. "europe-west1")
5. Vælg **"Start in test mode"** (vi ændrer regler senere)
6. Klik **"Enable"**

### 3. Konfigurer Database Regler

For at tillade læsning og skrivning til highscores:

1. Gå til **"Rules"** tab i Realtime Database
2. Erstat reglerne med følgende:

```json
{
  "rules": {
    "highscores": {
      ".read": true,
      "$username": {
        ".write": true,
        ".validate": "newData.hasChildren(['username', 'score', 'timestamp'])"
      }
    }
  }
}
```

3. Klik **"Publish"**

**Hvad gør disse regler?**
- Alle kan læse highscores (`.read: true`)
- Alle kan skrive deres egen score (`.write: true`)
- Validerer at data indeholder username, score og timestamp

### 4. Hent Firebase Config

1. Gå til **Project Settings** (tandhjul ikon øverst til venstre)
2. Scroll ned til **"Your apps"**
3. Klik på **"</>"** (Web app) ikonet
4. Giv appen et navn (f.eks. "Flappy Eagle Web")
5. Klik **"Register app"**
6. Kopier `firebaseConfig` objektet

Det ser sådan ud:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "flappy-eagle-xxxxx.firebaseapp.com",
  databaseURL: "https://flappy-eagle-xxxxx-default-rtdb.europe-west1.firebasedatabase.app",
  projectId: "flappy-eagle-xxxxx",
  storageBucket: "flappy-eagle-xxxxx.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef123456"
};
```

### 5. Opdater index.html

1. Åbn `index.html` i en editor
2. Find linjen med `const firebaseConfig = {` (omkring linje 1906)
3. Erstat hele `firebaseConfig` objektet med dit eget fra Firebase Console
4. Gem filen

**Før:**
```javascript
const firebaseConfig = {
    apiKey: "DIN-API-KEY",
    authDomain: "dit-projekt.firebaseapp.com",
    databaseURL: "https://dit-projekt.firebaseio.com",
    // ...
};
```

**Efter:**
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXX",
    authDomain: "flappy-eagle-xxxxx.firebaseapp.com",
    databaseURL: "https://flappy-eagle-xxxxx-default-rtdb.europe-west1.firebasedatabase.app",
    // ... (din egen config)
};
```

### 6. Test Funktionaliteten

1. Åbn `index.html` i en browser
2. Åbn Developer Console (F12)
3. Du skulle se: `✅ Firebase initialiseret!`
4. Spil et spil og få en score
5. Klik på **"🏆 Global Highscore"** knappen
6. Din score skulle nu vises i listen!

## 🔒 Sikkerhed

### Produktions-Regler (Anbefalet)

For bedre sikkerhed i produktion, brug disse regler:

```json
{
  "rules": {
    "highscores": {
      ".read": true,
      "$username": {
        ".write": "!data.exists() || newData.child('score').val() > data.child('score').val()",
        ".validate": "newData.hasChildren(['username', 'score', 'timestamp']) && newData.child('score').isNumber() && newData.child('score').val() >= 0 && newData.child('score').val() <= 10000"
      }
    }
  }
}
```

**Hvad gør disse regler?**
- Kun tillad opdatering hvis ny score er højere end eksisterende
- Valider at score er et tal mellem 0 og 10000
- Forhindrer spam og manipulation

### Rate Limiting

Firebase har automatisk rate limiting, men du kan også:

1. Gå til **"Usage"** tab i Realtime Database
2. Sæt limits for samtidig forbindelser
3. Overvåg usage for at opdage misbrug

## 🐛 Fejlfinding

### "Firebase not defined"
- Tjek at Firebase SDK scripts er indlæst korrekt i `<head>`
- Tjek browser console for fejl

### "Permission denied"
- Tjek at database regler tillader læsning/skrivning
- Tjek at `databaseURL` er korrekt i config

### "Highscores vises ikke"
- Åbn Firebase Console → Realtime Database → Data
- Tjek om data bliver gemt korrekt
- Tjek browser console for fejl

### "CORS errors"
- Firebase skulle håndtere CORS automatisk
- Hvis problemer, tjek at du bruger HTTPS (ikke file://)

## 📊 Database Struktur

Sådan ser data ud i Firebase:

```
highscores/
  ├── user1/
  │   ├── username: "user1"
  │   ├── score: 42
  │   ├── timestamp: 1234567890
  │   └── date: "2024-01-15T10:30:00.000Z"
  ├── user2/
  │   ├── username: "user2"
  │   ├── score: 38
  │   └── ...
  └── ...
```

## 💡 Tips

- **Gratis Tier**: Firebase Realtime Database har en generøs gratis tier
- **Backup**: Eksporter data regelmæssigt fra Firebase Console
- **Monitoring**: Overvåg usage i Firebase Console
- **Testing**: Test med forskellige brugere og scores

## 🆘 Support

Hvis du har problemer:
1. Tjek Firebase Console for fejlmeddelelser
2. Åbn browser Developer Console (F12)
3. Læs fejlmeddelelserne nøje
4. Google fejlmeddelelsen + "Firebase Realtime Database"

## 📚 Ressourcer

- [Firebase Documentation](https://firebase.google.com/docs/database)
- [Firebase Console](https://console.firebase.google.com/)
- [Firebase Pricing](https://firebase.google.com/pricing)

---

**Held og lykke! 🚀**
