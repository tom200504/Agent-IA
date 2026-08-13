Agent IA Immo — Landing page & automatisation de leads

Solution complète pour agences immobilières indépendantes : un agent IA qui qualifie, répond et relance automatiquement les leads entrants (acheteurs et vendeurs), du premier contact jusqu'à la prise de rendez-vous.

🔗 Démo en ligne : agent-ia-tom.web.app ▶️ Démo vidéo (~5 min) : voir sur Loom

Ce repo contient le code de la landing page (ce qu'un prospect voit). L'automatisation elle-même tourne sur Make.com + l'API OpenAI — les captures ci-dessous montrent ce qui se passe derrière.

<img width="1477" height="785" alt="image" src="https://github.com/user-attachments/assets/2e2bea97-90c1-46be-aa5f-4ed06fe80a49" />


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

<img width="381" height="662" alt="image" src="https://github.com/user-attachments/assets/e403e209-a07a-4c9f-be6e-55225f7e5418" />



Le lead remplit un formulaire Tally, l'IA analyse sa demande et le qualifie, le système route la conversation selon qu'il s'agit d'un projet d'achat ou de vente, un email personnalisé part automatiquement, puis une relance se déclenche si le lead reste silencieux.

<img width="741" height="847" alt="image" src="https://github.com/user-attachments/assets/f184d948-ad9c-43d5-8878-ba67e0286f3a" />


L'automatisation derrière (Make.com)

Trois scénarios Make orchestrent l'ensemble : capture du lead, qualification par IA, et relances programmées.

<img width="1532" height="272" alt="scenarios-overview" src="https://github.com/user-attachments/assets/5b36f5c4-7afa-4199-aec3-4dd04df07577" />


Acquisition / premier contact — capture le lead depuis Tally, l'enregistre dans Google Sheets et route la notification selon le profil acheteur ou vendeur.

<img width="1681" height="727" alt="scenario-acquisition-premier-contact" src="https://github.com/user-attachments/assets/79bfed3d-c5f9-4261-9a9f-0955038fd245" />


Qualification par IA — lit les emails entrants, appelle l'API OpenAI pour analyser la demande, puis met à jour la fiche du lead avec un score et un résumé.

<img width="1600" height="738" alt="scenario-reponse-email-ia" src="https://github.com/user-attachments/assets/ff176b11-7609-41a5-87d0-8dc6028704b3" />


Relance J+1 / J+3 — vérifie toutes les 2 heures les leads sans réponse et déclenche l'email de relance approprié.

<img width="1516" height="732" alt="scenario-relance-j1-j3" src="https://github.com/user-attachments/assets/a84a5eb3-41e6-4056-b9ed-9e5d9722a91f" />


Résultat côté agence

<img width="1048" height="411" alt="image" src="https://github.com/user-attachments/assets/1e314b91-7f41-45c2-98a6-7b17339a70a9" />


<img width="1736" height="340" alt="image" src="https://github.com/user-attachments/assets/35828f47-4cca-408f-bc37-38f4e9348e68" />


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
