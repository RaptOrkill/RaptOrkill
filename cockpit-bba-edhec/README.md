# Cockpit BBA EDHEC 🎓

Outil tout-en-un pour l'International BBA de l'EDHEC (French Track) : une seule page web, utilisable sur téléphone, tablette et ordinateur, avec synchronisation entre appareils.

## Fonctionnalités

- **Accueil** — cours du jour, échéances à venir, cartes à réviser, moyenne générale, ECTS validés, temps de focus
- **Agenda** — emploi du temps hebdomadaire avec **import iCal (.ics) depuis MyEDHEC / Aurion**, créneaux récurrents ou ponctuels, types (cours, TD, langue, examen)
- **Cours** — matières avec ECTS, notes coefficientées, moyennes automatiques (pondérées ECTS), crédits validés
- **Tâches** — kanban (à faire / en cours / fait), échéances, ajout rapide, lien avec les matières
- **Réviser** — flashcards à répétition espacée (type SM-2) + minuteur Pomodoro 25/5 avec suivi quotidien
- **Réglages** — profil, thème clair/sombre/auto, sauvegarde & restauration JSON

## Architecture

Un seul fichier `index.html` : HTML + CSS + JavaScript vanilla, zéro dépendance.
Publié comme Artifact Claude : l'app enregistre ses propres versions, ce qui synchronise les données entre tous les appareils qui ouvrent le même lien. Repli automatique sur `localStorage` hors connexion.

> La connexion directe au compte MyEDHEC n'est pas possible (identifiants privés) : l'import passe par l'export iCal du planning, refais-le à chaque mise à jour.
