# Sauvez l’entreprise ! — jeu multijoueur

## Fonctionnalités
- Code de partie et nom/pseudonyme par étudiant.
- 10 questions sur la fonction de production de courte période.
- Réponses individuelles et conséquences sur bénéfices, budget, clients et santé.
- Tableau de bord administrateur en temps réel.
- Classement et export CSV.

## Hébergement simple sur Render
1. Crée un compte GitHub et un compte Render.
2. Décompresse le ZIP puis téléverse les fichiers dans un dépôt GitHub.
3. Sur Render, sélectionne **New + → Blueprint** et relie ce dépôt. Render détecte `render.yaml`.
4. Définis `ADMIN_PASSWORD` avec un mot de passe privé, puis déploie.
5. Render fournit une adresse publique `https://...onrender.com`.

Alternative : créer un Web Service depuis le dépôt, commande de build `npm install`, commande de démarrage `npm start`, et ajouter la variable `ADMIN_PASSWORD`.

## Le jour de l’exposé
1. Ouvre `https://TON-SITE.onrender.com/admin.html`.
2. Saisis le mot de passe pour créer une partie.
3. Partage le lien public et le code affiché.
4. Les étudiants ouvrent le lien, saisissent le code et leur nom.
5. Clique **Lancer la partie** ; après chaque question, consulte les réponses puis clique **Question suivante**.
6. À la fin, exporte le classement en CSV.

## Tester sur ton ordinateur
Node.js 18+ requis :
```bash
npm install
ADMIN_PASSWORD='mon-mot-de-passe' npm start
```
Puis ouvre `http://localhost:3000` (étudiants) et `http://localhost:3000/admin.html` (administrateur).

## Limites à connaître
- Les parties sont stockées en mémoire : un redémarrage du serveur efface les sessions.
- Il n’y a pas de reconnexion automatique d’un joueur déconnecté dans cette première version.
- Les étudiants doivent avoir Internet et garder leur page ouverte.
- Configure impérativement `ADMIN_PASSWORD` avant de partager le site. Le mot de passe de secours par défaut est `change-moi-avant-de-jouer`.
- Pour une activité pédagogique, un prénom ou pseudonyme suffit ; ne collecte pas d’informations personnelles.
