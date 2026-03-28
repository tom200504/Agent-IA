# Agent IA Immo — Landing Page

## 🔧 3 choses à remplacer avant de publier

Recherche `LIEN_CALENDLY_ICI`, `LIEN_LOOM_ICI` et `VOTRE_EMAIL_ICI` dans `public/index.html` et remplace-les par tes vraies valeurs (4 occurrences au total).

---

## 🚀 Déployer sur Firebase Hosting

### 1. Installer Firebase CLI (une seule fois)
```bash
npm install -g firebase-tools
```

### 2. Se connecter
```bash
firebase login
```

### 3. Initialiser le projet Firebase
```bash
firebase use --add
# Sélectionne ton projet Firebase (ou crée-en un sur console.firebase.google.com)
```
→ Mets le bon `project_id` dans `.firebaserc`

### 4. Déployer
```bash
firebase deploy --only hosting
```

Firebase te donnera une URL du type `https://ton-projet.web.app` ✅

---

## 📁 Structure
```
agent-ia-immo/
├── public/
│   └── index.html      ← tout le site (HTML + CSS + JS intégrés)
├── firebase.json       ← config hosting
├── .firebaserc         ← lien vers ton projet Firebase
└── README.md
```

## ✏️ Modifier le contenu
Tout est dans `public/index.html`. Pas de build nécessaire, pas de dépendances.
