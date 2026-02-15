# 🦅 Flappy Eagle

Et moderne Flappy Bird-spil med 3D-grafik, skins, vejreffekter og meget mere!

![Flappy Eagle](https://img.shields.io/badge/Status-Active-success)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?logo=pwa)

## 🎮 Spil Nu!

**[Spil Flappy Eagle →](https://[dit-brugernavn].github.io/flappy-eagle/)**

## ✨ Features

### 🎨 Grafik & Design
- **3D Ørn** med realistiske vinger, næb og øjne
- **Vejreffekter**: Dag, nat, regn, torden, sne
- **Animerede skyer** og partikelsystemer
- **Flotte farver** og gradients

### 🎯 Gameplay
- **3 Sværhedsgrader**: Let, Medium, Svær
- **Custom Mode**: Tilpas alle spilindstillinger
- **Bevægelige rør**: Rørene bevæger sig efter 5 point
- **Stigende hastighed**: Spillet bliver hurtigere over tid
- **God Mode**: For admin/testing

### 🎭 Skins System
- **10+ Forskellige skins** at låse op
- **Mønter system**: Tjen mønter ved at spille
- **Skin shop**: Køb nye skins med mønter
- Skins inkluderer: Standard Ørn, Gul Fugl, Rød Kardinal, Blå Jay, Grøn Papegøje, og flere!

### 👑 Admin Features
- **Admin panel** med engangskoder
- **Vejr kontrol**: Skift vejr i realtid
- **Rør farver**: Skift farve på rørene
- **Besked system**: Send beskeder til alle spillere
- **Mønter management**: Giv mønter til spillere

### 📱 Progressive Web App (PWA)
- **Installer som app** på mobil og desktop
- **Offline support** med Service Worker
- **Fuld skærm mode** på mobil
- **Touch optimeret** til mobil med active feedback
- **Responsivt design** med 4 breakpoints (768px, 480px, 360px, landscape)
- **Optimeret for alle skærmstørrelser** - fra iPhone SE til iPad
- **Bedre touch targets** (minimum 48x48px)
- **Ingen zoom** - perfekt mobil oplevelse

### 🏆 Global Highscore
- **Firebase Realtime Database** integration
- Se de bedste spillere globalt
- Sammenlign din score med andre
- Realtime opdateringer
- Automatisk upload af nye rekorder

## 🚀 Kom I Gang

### Spil Online
Besøg bare [GitHub Pages linket](https://[dit-brugernavn].github.io/flappy-eagle/) og begynd at spille!

### 🔥 Opsæt Firebase (Valgfrit)
For at aktivere global highscore funktionalitet:

1. Læs **[FIREBASE_SETUP.md](FIREBASE_SETUP.md)** for detaljerede instruktioner
2. Opret et gratis Firebase projekt
3. Aktiver Realtime Database
4. Opdater `firebaseConfig` i `index.html`
5. Færdig! Highscores synkroniseres nu globalt

**Note:** Spillet virker perfekt uden Firebase - highscores gemmes lokalt.

### Installer Som App
1. Åbn spillet i din browser
2. Klik på "📱 Installer App" knappen
3. Følg instruktionerne
4. Spil offline når som helst!

### Kør Lokalt
```bash
# Klon repository
git clone https://github.com/[dit-brugernavn]/flappy-eagle.git

# Åbn index.html i din browser
# Eller brug en lokal server:
python -m http.server 8000
# Besøg http://localhost:8000
```

## 📱 Mobile Optimizations

Flappy Eagle er fuldt optimeret til mobil! Se [MOBILE_OPTIMIZATIONS.md](MOBILE_OPTIMIZATIONS.md) for detaljer.

### ✨ Mobile Features:
- **Touch controls** - Tap anywhere to fly
- **Active feedback** - Buttons respond instantly
- **Responsive layout** - Works on all screen sizes
- **Landscape support** - Play in any orientation
- **No zoom** - Perfect fullscreen experience
- **PWA ready** - Add to home screen

### 📱 Tested On:
- ✅ iPhone SE, 12, 13, 14, Pro Max
- ✅ Samsung Galaxy S21, S22
- ✅ iPad & Android tablets
- ✅ All major mobile browsers

## 🎮 Sådan Spiller Du

### Kontroller
- **Desktop:** Mellemrum / Klik / Hold musen nede
- **Mobile:** Tap anywhere på skærmen

### Mål
- Flyv gennem rørene uden at ramme dem
- Tjen point for hvert rør du passerer
- Tjen mønter (1 mønt per 2 point)
- Lås nye skins op i shoppen

### Tips
- Start med **Let** mode for at øve dig
- Brug **Custom Mode** til at finde din ideelle sværhedsgrad
- Saml mønter til at låse alle skins op
- Prøv forskellige vejreffekter for variation

## 🛠️ Teknologi

- **HTML5 Canvas** til rendering
- **Vanilla JavaScript** - ingen dependencies
- **CSS3** med animationer og gradients
- **LocalStorage** til at gemme fremskridt
- **PWA** med Service Worker
- **Firebase** (kommer snart) til global highscore

## 📊 Sværhedsgrader

| Mode | Tyngdekraft | Hop Styrke | Rør Hastighed | Rør Afstand |
|------|-------------|------------|---------------|-------------|
| **Let** | 0.4 | -9 | 3 | 300px |
| **Medium** | 0.6 | -10 | 4 | 250px |
| **Svær** | 0.8 | -11 | 5 | 200px |
| **Custom** | Valgfri | Valgfri | Valgfri | Valgfri |

## 🎨 Tilgængelige Skins

- 🦅 **Standard Ørn** (Gratis)
- 🐥 **Gul Fugl** (50 mønter)
- 🔴 **Rød Kardinal** (100 mønter)
- 🔵 **Blå Jay** (150 mønter)
- 🟢 **Grøn Papegøje** (200 mønter)
- 🟣 **Lilla Fugl** (250 mønter)
- 🟠 **Orange Fugl** (300 mønter)
- ⚫ **Sort Ravn** (400 mønter)
- ⚪ **Hvid Due** (500 mønter)
- 🌈 **Regnbue Fugl** (1000 mønter)

## 🤝 Bidrag

Bidrag er velkomne! Åbn gerne issues eller pull requests.

### Udvikling
```bash
# Fork projektet
# Lav dine ændringer
# Test grundigt
# Submit en pull request
```

## 📝 Licens

Dette projekt er open source og tilgængeligt under [MIT License](LICENSE).

## 👨‍💻 Udvikler

Lavet med ❤️ af [Dit Navn]

## 🙏 Anerkendelser

- Inspireret af det originale Flappy Bird spil
- Emoji ikoner fra Unicode
- Tak til alle der spiller!

## 📞 Kontakt

- GitHub: [@dit-brugernavn](https://github.com/dit-brugernavn)
- Issues: [Rapporter bugs](https://github.com/dit-brugernavn/flappy-eagle/issues)

---

**Hav det sjovt og flap dig til sejren! 🦅✨**
