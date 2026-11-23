<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.png">
  <img alt="Jules Neveu, développeur à Nantes" src="assets/banner-light.png" width="100%">
</picture>

<p align="center">
  <a href="https://app-25fa744b-25eb-4ea0-9d7e-88fe870d5552.cleverapps.io">Portfolio</a> ·
  <a href="https://www.linkedin.com/in/jules-neveu-167645258">LinkedIn</a> ·
  <a href="mailto:neveu.jules58@gmail.com">neveu.jules58@gmail.com</a>
</p>

Je développe surtout des outils que j'utilise moi-même : une assistante vocale qui tourne chez moi, une application de bureau pour travailler avec Claude Code, des skills pour agents IA.

Ce qui m'intéresse, c'est l'architecture. Comment les parties d'un système communiquent, ce qui se passe quand l'une d'elles tombe, et comment le faire tourner dans la durée. Je touche à plusieurs domaines (backend, applications desktop, IA locale, Linux) et j'apprends en construisant.

## Ma façon de travailler

- **Le modèle propose, le code décide.** Dans ORION comme dans Aether, une IA ne déclenche jamais seule une action risquée : le programme valide, vérifie les droits et demande confirmation.
- **Je teste ce que je livre.** Vitest et Playwright sur Aether, tests Go sur le forum, une suite de tests sur ORION.
- **Je vais jusqu'à la mise en service.** ORION tourne en service sur un serveur Linux, mon portfolio est hébergé sur Clever Cloud.
- **J'écris ce qui manque.** Chaque projet documente son installation, et ses limites connues quand il en a.

## Projets

### ORION · assistante vocale locale

Une assistante vocale qui pilote ma maison et mon PC sans envoyer aucune donnée dans le cloud. Elle tourne sur trois machines de mon réseau : un mini-PC Linux qui coordonne tout, un PC portable avec GPU pour le modèle de langage, et mon PC principal pour le micro, les haut-parleurs et l'application de supervision.

- Le modèle de langage ne fait que proposer une action. Un noyau d'outils la valide, vérifie les permissions, demande confirmation si besoin et garde une trace de tout.
- Les commandes courantes (lumières, musique, minuteurs, rappels) passent sans modèle de langage : l'assistante reste utilisable quand le GPU est éteint.
- Mot de réveil entraîné pour elle, transcription et synthèse vocale en local, appels téléphoniques chiffrés, application mobile.

`Python` `Ollama` `faster-whisper` `Piper` `openWakeWord` `SQLite` `systemd` `Docker` `Expo`

**État :** en production chez moi depuis novembre 2026. Dépôt privé, [étude de cas sur mon portfolio](https://app-25fa744b-25eb-4ea0-9d7e-88fe870d5552.cleverapps.io/orion.html).

### [Aether](https://github.com/NardenLaSouris/aether) · poste de travail pour Claude Code

Une application de bureau Windows qui pilote Claude Code, installé sur la machine. Plusieurs conversations en parallèle, les limites d'usage toujours visibles, chaque tâche dans sa propre branche Git jusqu'à la pull request, et des mods pour modifier l'interface.

- Le SDK de Claude tourne dans un processus séparé : s'il plante, l'application reste ouverte et il redémarre seul.
- L'interface n'a pas accès à Node.js. Chaque échange avec le processus principal passe par une liste blanche validée avec zod.
- Rien de destructeur sans confirmation : push, suppression d'une branche de travail, commande envoyée par un mod.

`TypeScript` `Electron` `React` `Tailwind` `Zustand` `Claude Agent SDK` `Vitest` `Playwright`

**État :** en développement (v0.2.0), Windows uniquement.

### [Forum-Project](https://github.com/NardenLaSouris/Forum-Project) · forum web en équipe

Un forum inspiré de Reddit, réalisé en équipe : comptes et sessions, publications par catégories, commentaires, likes et dislikes.

- Serveur Go sans framework web, pages rendues côté serveur avec les templates Go.
- Mots de passe hachés avec bcrypt, sessions par cookie, base SQLite.
- Tests Go sur les routes et les likes, Dockerfile pour le lancer.

`Go` `SQLite` `HTML` `CSS` `JavaScript` `Docker`

**État :** terminé.

### [Projet_RPG_TypeScript](https://github.com/NardenLaSouris/Projet_RPG_TypeScript) · RPG en équipe

Un jeu de rôle au tour par tour dans le terminal, à trois. On compose une équipe de trois aventuriers parmi six classes, on traverse cinq salles et on affronte un boss.

- Programmation orientée objet : chaque classe de personnage et chaque monstre hérite d'une base commune et redéfinit ses actions.
- Ordre des tours selon la vitesse, actions propres à chaque classe, inventaire partagé.

`TypeScript` `Deno`

**État :** terminé.

### Skills pour agents IA

J'écris aussi des skills : des instructions packagées qu'un agent comme Claude Code charge pour faire une tâche précise. Exemple public : [`/unslop`](https://github.com/NardenLaSouris/portfolio-/blob/main/.claude/skills/unslop/SKILL.md), qui relit les textes d'un site et réécrit les tournures qui sonnent « générées par une IA », sans toucher aux faits.

### Autres projets

- [**portfolio-**](https://github.com/NardenLaSouris/portfolio-) · mon portfolio : HTML, CSS et JavaScript sans framework, servi par un petit serveur Node.js sans dépendance.
- [**Hangman-classic**](https://github.com/NardenLaSouris/Hangman-classic) · pendu en Go organisé en paquets : difficultés, codes de triche, mode deux joueurs.
- [**Projet-red**](https://github.com/NardenLaSouris/Projet-red) · jeu de rôle en Go dans le terminal : classes, marché, forgeron, combats.
- [**GalaxiEat**](https://github.com/NardenLaSouris/GalaxiEat) · base de données SQL d'une chaîne de restaurants, de la modélisation aux requêtes d'analyse.
- [**ATELIER TODO App**](https://github.com/NardenLaSouris/ATELIER-FIL-CONDUCTEUR---TODO-APP) · atelier de déploiement en binôme : serveur Express, connexion PostgreSQL, mise en ligne sur Scalingo.
- **AI-LOCAL-MODEL** · prototype de questions-réponses sur un document, entièrement en local (FAISS et Ollama). Dépôt privé.
- Mes premiers programmes en Python : [Puissance 4](https://github.com/NardenLaSouris/connect-4-python), [solveur de Sudoku](https://github.com/NardenLaSouris/Sudoku-Solver-Python), [pendu](https://github.com/NardenLaSouris/Hangman-Python). Et mes exercices d'algorithmique en Go : [Piscine Go](https://github.com/NardenLaSouris/Piscine-go-nantes-2526).

## Technologies

Uniquement ce que j'ai utilisé dans les projets ci-dessus.

- **Langages :** Python, Go, TypeScript, JavaScript, SQL, HTML, CSS
- **Frontend :** React, Tailwind CSS, Zustand, interfaces sans framework
- **Backend :** Node.js, Express, serveurs HTTP en Go
- **Desktop :** Electron
- **IA :** Ollama, faster-whisper, Piper, openWakeWord, sentence-transformers, FAISS, Claude Agent SDK
- **Données :** SQLite, PostgreSQL
- **Infrastructure :** Linux (Ubuntu), systemd, Docker, Clever Cloud, Scalingo
- **Outils :** Git et GitHub, Vitest, Playwright, ESLint, Deno, Bash, PowerShell

---

<sub>Originaire de la Nièvre, basé à Nantes. En dehors du code : le jeu vidéo et le matériel informatique. ORION sait d'ailleurs allumer ma PS5 à la voix.</sub>
