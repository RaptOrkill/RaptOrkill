# Cockpit BBA EDHEC 🎓

Outil tout-en-un pour l'International BBA de l'EDHEC (French Track) : une seule page web, utilisable sur téléphone, tablette et ordinateur, avec synchronisation entre appareils.

## Fonctionnalités

- **Accueil** — plan du jour généré automatiquement (retards, rendus, prochain cours, examens à J−7, cartes à réviser), moyenne générale, ECTS validés, focus du jour
- **Agenda** — emploi du temps hebdomadaire, **import iCal (.ics) depuis MyEDHEC / Aurion**, une couleur par matière, examens en rouge
- **Cours** — matières avec ECTS et moyennes pondérées automatiques + **prise de notes par matière** ; les lignes `terme = définition` se transforment en flashcards d'un clic
- **Tâches** — kanban (à faire / en cours / fait) ; les examens importés créent automatiquement leurs rappels de révision J−7 et J−1
- **Réviser** — flashcards à répétition espacée (type SM-2) + minuteur Pomodoro 25/5
- **Micro** — dictaphone de cours : enregistre, met en pause, réécoute et exporte tes cours (stockage local IndexedDB, titre pré-rempli d'après l'agenda)

## Automatisations

- Import .ics → création automatique des matières (avec couleurs) et liaison des créneaux
- Examens détectés → tâches de révision J−7 / J−1 (dédupliquées, purgées si l'examen disparaît)
- Nettoyage automatique : créneaux passés depuis 45 j, tâches faites depuis 14 j
- Plan du jour recalculé à chaque ouverture

## Architecture

Un seul fichier `index.html` : HTML + CSS + JavaScript vanilla, zéro dépendance, un seul bloc de script (la page se re-publie elle-même pour synchroniser les données ; le bloc unique garantit une copie complète du document).
Publié comme Artifact Claude ; repli `localStorage` hors connexion. Audio en IndexedDB (local à l'appareil, export via la capacité downloads).

> La connexion directe au compte MyEDHEC (identifiants) n'existe pas et ne doit pas exister : le planning passe par l'export iCal, à refaire à chaque mise à jour.
