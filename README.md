Agent IA Immo — Landing page & automatisation de leads

Solution complète pour agences immobilières indépendantes : un agent IA qui qualifie, répond et relance automatiquement les leads entrants (acheteurs et vendeurs), du premier contact jusqu'à la prise de rendez-vous.

🔗 Démo en ligne : agent-ia-tom.web.app ▶️ Démo vidéo (~5 min) : voir sur Loom

Ce repo contient le code de la landing page (ce qu'un prospect voit). L'automatisation elle-même tourne sur Make.com + l'API OpenAI — les captures ci-dessous montrent ce qui se passe derrière.

Afficher l'image

Le problème résolu

Une agence immobilière met en moyenne 4 à 6 heures à répondre à un lead entrant. Le temps de répondre, le prospect a déjà contacté deux autres agences, et sans relance structurée, 30 à 50 % des leads ne reçoivent jamais de suivi. L'agent IA répond en moins de 3 minutes, qualifie automatiquement acheteur ou vendeur, et relance les leads silencieux à J+1 et J+3.

Fonctionnalités
Réponse automatique en moins de 3 minutes, 7j/7
Qualification par IA (acheteur / vendeur), avec questions adaptées au profil
Relances automatiques J+1 et J+3 pour les leads sans réponse
Score IA et résumé structuré envoyé à l'agence par email
Prise de rendez-vous automatique (Calendly) pour les leads chauds
Suivi en temps réel dans une feuille Google Sheets
Comment ça marche

<img width="741" height="847" alt="image" src="https://github.com/user-attachments/assets/66ad4475-266d-4aa8-bc8f-1daa4275f250" />


Le lead remplit un formulaire Tally, l'IA analyse sa demande et le qualifie, le système route la conversation selon qu'il s'agit d'un projet d'achat ou de vente, un email personnalisé part automatiquement, puis une relance se déclenche si le lead reste silencieux.

Afficher l'image

L'automatisation derrière (Make.com)

Trois scénarios Make orchestrent l'ensemble : capture du lead, qualification par IA, et relances programmées.

Afficher l'image

Acquisition / premier contact — capture le lead depuis Tally, l'enregistre dans Google Sheets et route la notification selon le profil acheteur ou vendeur.

Afficher l'image

Qualification par IA — lit les emails entrants, appelle l'API OpenAI pour analyser la demande, puis met à jour la fiche du lead avec un score et un résumé.

Afficher l'image

Relance J+1 / J+3 — vérifie toutes les 2 heures les leads sans réponse et déclenche l'email de relance approprié.

Afficher l'image

Résultat côté agence

Afficher l'image

Afficher l'image

Stack technique
Brique	Rôle
Firebase Hosting	Hébergement de la landing page
Tally	Formulaire de capture des leads
Make.com	Orchestration de l'automatisation
OpenAI API	Qualification et rédaction des réponses
Gmail	Envoi des emails et relances
Google Sheets	Suivi et historique des leads
Calendly	Prise de rendez-vous pour les leads chauds
Déployer ce repo
1. Installer Firebase CLI (une seule fois)
bash
npm install -g firebase-tools
2. Se connecter
bash
firebase login
3. Initialiser le projet Firebase
bash
firebase use --add
# Sélectionne ton projet Firebase (ou crée-en un sur console.firebase.google.com)

→ Mets le bon project_id dans .firebaserc

4. Déployer
bash
firebase deploy --only hosting

Firebase donne une URL du type https://ton-projet.web.app

Structure
agent-ia-immo/
├── public/
│   └── index.html      ← tout le site (HTML + CSS + JS intégrés)
├── screenshots/         ← captures utilisées dans ce README
├── firebase.json        ← config hosting
├── .firebaserc          ← lien vers le projet Firebase
└── README.md
Auteur

tom200504 — solution conçue et développée en solo, du script d'automatisation jusqu'à la landing page commerciale.
