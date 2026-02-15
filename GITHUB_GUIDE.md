# 📦 GitHub Upload & Deployment Guide

Denne guide hjælper dig med at få Flappy Eagle på GitHub og live på internettet!

## 🎯 Hvad Du Får

- ✅ Kode på GitHub (versionskontrol, backup)
- ✅ Live spil på internettet (GitHub Pages)
- ✅ Automatisk deployment (push = live)
- ✅ Gratis hosting

## 📋 Forudsætninger

### 1. Installer Git

**Windows:**
1. Download Git fra [git-scm.com](https://git-scm.com/download/win)
2. Kør installeren (brug standard indstillinger)
3. Genstart terminalen

**Mac:**
```bash
# Installer via Homebrew
brew install git

# Eller download fra git-scm.com
```

**Linux:**
```bash
sudo apt-get install git  # Ubuntu/Debian
sudo yum install git      # CentOS/RHEL
```

### 2. Opret GitHub Konto

1. Gå til [github.com](https://github.com)
2. Klik **"Sign up"**
3. Følg instruktionerne
4. Verificer din email

## 🚀 Trin-for-Trin Guide

### Trin 1: Initialiser Git Repository

Åbn terminal/PowerShell i projektmappen:

```bash
# Initialiser git
git init

# Tilføj alle filer
git add .

# Lav første commit
git commit -m "🎮 Initial commit - Flappy Eagle spil"
```

### Trin 2: Opret GitHub Repository

1. Gå til [github.com/new](https://github.com/new)
2. **Repository name:** `flappy-eagle` (eller dit eget navn)
3. **Description:** "🦅 Et moderne Flappy Bird spil med 3D grafik, skins og global highscore"
4. **Public** (så andre kan se det)
5. **IKKE** tilføj README, .gitignore eller license (vi har dem allerede)
6. Klik **"Create repository"**

### Trin 3: Push Til GitHub

GitHub viser dig kommandoer - brug disse:

```bash
# Tilføj GitHub som remote
git remote add origin https://github.com/[dit-brugernavn]/flappy-eagle.git

# Omdøb branch til main (hvis nødvendigt)
git branch -M main

# Push til GitHub
git push -u origin main
```

**Første gang:** GitHub vil bede om login
- Brug dit GitHub brugernavn
- Password: Brug en **Personal Access Token** (ikke dit password!)

#### Opret Personal Access Token:
1. Gå til [github.com/settings/tokens](https://github.com/settings/tokens)
2. Klik **"Generate new token"** → **"Generate new token (classic)"**
3. Giv den et navn (f.eks. "Flappy Eagle")
4. Vælg **"repo"** scope
5. Klik **"Generate token"**
6. **KOPIER TOKEN NU** (du kan ikke se den igen!)
7. Brug denne som password når du pusher

### Trin 4: Aktiver GitHub Pages

1. Gå til dit repository på GitHub
2. Klik **"Settings"** (øverst til højre)
3. Klik **"Pages"** i venstre menu
4. Under **"Source"**:
   - Vælg **"GitHub Actions"**
5. Klik **"Save"**

### Trin 5: Vent På Deployment

1. Gå til **"Actions"** tab i dit repository
2. Du skulle se en workflow køre
3. Vent til den er færdig (grøn checkmark ✅)
4. Gå tilbage til **"Settings"** → **"Pages"**
5. Du skulle nu se et link: `https://[dit-brugernavn].github.io/flappy-eagle/`

**🎉 TILLYKKE! Dit spil er nu live!**

## 🔄 Opdater Spillet

Når du laver ændringer:

```bash
# Se ændringer
git status

# Tilføj ændringer
git add .

# Commit med besked
git commit -m "✨ Tilføjet ny feature"

# Push til GitHub
git push
```

**Automatisk deployment:** Hver gang du pusher, deployes spillet automatisk!

## 📝 Opdater README

Husk at opdatere links i README.md:

1. Åbn `README.md`
2. Erstat `[dit-brugernavn]` med dit faktiske GitHub brugernavn
3. Erstat `[Dit Navn]` med dit navn
4. Commit og push ændringerne

## 🎨 Tilpas Spillet

### Opdater Titel og Beskrivelse

I `index.html`, find og ændre:
- `<title>Flappy Eagle</title>` (linje 6)
- Meta description (linje 15)

### Tilføj Dit Navn

I README.md:
- Opdater "Udvikler" sektionen
- Tilføj dine kontaktoplysninger

## 🐛 Fejlfinding

### "Git not found"
- Installer Git (se forudsætninger)
- Genstart terminal efter installation

### "Permission denied"
- Brug Personal Access Token i stedet for password
- Tjek at token har "repo" scope

### "Pages not working"
- Vent 2-5 minutter efter første deployment
- Tjek at GitHub Actions workflow er kørt succesfuldt
- Tjek at repository er Public (ikke Private)

### "404 Not Found"
- Tjek at `index.html` er i rod-mappen
- Tjek at GitHub Pages er aktiveret
- Vent et par minutter og prøv igen

## 📊 GitHub Features

### Issues
Brug Issues til at tracke bugs og features:
1. Gå til **"Issues"** tab
2. Klik **"New issue"**
3. Beskriv bug/feature
4. Tilføj labels

### Releases
Lav releases når du når milepæle:
1. Gå til **"Releases"**
2. Klik **"Create a new release"**
3. Tag: `v1.0.0`
4. Titel: "🎮 Version 1.0 - Initial Release"
5. Beskriv ændringer

### README Badges
Tilføj badges til README:
```markdown
![GitHub stars](https://img.shields.io/github/stars/[brugernavn]/flappy-eagle)
![GitHub forks](https://img.shields.io/github/forks/[brugernavn]/flappy-eagle)
![GitHub issues](https://img.shields.io/github/issues/[brugernavn]/flappy-eagle)
```

## 🌟 Promover Dit Spil

1. **Del linket** på sociale medier
2. **Tilføj til din portfolio**
3. **Submit til spil-websites**
4. **Bed venner om at starre** repository
5. **Skriv en blog post** om udviklingen

## 💡 Næste Skridt

- [ ] Opsæt Firebase (se FIREBASE_SETUP.md)
- [ ] Tilføj custom domain (valgfrit)
- [ ] Tilføj Google Analytics (valgfrit)
- [ ] Lav en trailer video
- [ ] Skriv en devlog

## 📚 Ressourcer

- [GitHub Docs](https://docs.github.com)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Markdown Guide](https://www.markdownguide.org/)

## 🆘 Hjælp

Hvis du sidder fast:
1. Læs fejlmeddelelsen nøje
2. Google fejlmeddelelsen
3. Tjek GitHub Docs
4. Spørg på GitHub Discussions
5. Opret et Issue i dit repository

---

**Held og lykke med dit spil! 🚀🦅**
