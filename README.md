# NBA WTF Draft 🏀

Jeu de draft NBA humoristique, 2 joueurs, sur le même écran ou à distance. 80 joueurs, cinq choix par équipe, ordre serpent, scores WTF fictifs, recherche et catégories. Sans images externes ni API NBA.

## Publier sur GitHub Pages
1. Créez un dépôt public GitHub, par exemple `nba-wtf-draft`.
2. Envoyez **les fichiers contenus dans ce dossier à la racine du dépôt** (`index.html`, `app.js`, `players.js`, `firebase-config.js`, `firestore.rules`).
3. GitHub → Settings → Pages → Deploy from a branch → `main` → `/ (root)` → Save.
4. Le site sera disponible à `https://VOTRE-PSEUDO.github.io/nba-wtf-draft/` après déploiement. Le mode local fonctionne immédiatement.

## Activer les parties en ligne (Firebase)
1. Dans [Firebase Console](https://console.firebase.google.com/), créez un projet, ajoutez une application **Web**.
2. Copiez les champs `firebaseConfig` dans `firebase-config.js` (clé API, authDomain, projectId, appId). Ces identifiants web sont publics ; **ne mettez jamais de clé de compte de service**.
3. Authentication → Sign-in method → activez **Anonymous**.
4. Firestore Database → Create database (mode production), choisissez une région.
5. Firestore Database → Rules → remplacez par le contenu de `firestore.rules` et **publiez**.
6. Authentication → Settings → Authorized domains → ajoutez `VOTRE-PSEUDO.github.io` si nécessaire.
7. Envoyez `firebase-config.js` modifié sur GitHub. Rechargez le site.
8. Joueur A clique « Créer un salon » et partage le code affiché dans le titre ; joueur B saisit ce code puis « Rejoindre ».

## Limites et sécurité
- Les notes sont purement humoristiques. Pas de licence NBA, d'images ou de logos officiels.
- Les salons ne sont pas automatiquement supprimés. Vous pouvez les purger périodiquement depuis Firebase.
- La logique de validation de la liste des joueurs est principalement côté client ; pour un classement compétitif anti-triche, prévoir un backend Cloud Functions et une validation serveur complète.
- Une même session Firebase anonyme représente un seul joueur. Pour tester le mode en ligne, ouvrez un navigateur privé ou un autre appareil pour le deuxième joueur.
- Si les règles Firestore sont modifiées, vérifiez leur sécurité avant de rendre le jeu public.

## Annonce du Commissioner (V1.1)
Après chaque choix, une fenêtre de cérémonie annonce le numéro du pick, le joueur sélectionné et le nom de l'équipe qui le drafte (nom du participant). La voix de synthèse anglaise du navigateur prononce l'annonce ; il ne s'agit pas d'un enregistrement ou d'une imitation de la voix réelle d'Adam Silver. Le bouton Réécouter relance l'annonce. En mode en ligne, la fenêtre s'affiche sur les deux appareils lorsque le choix est synchronisé. La synthèse vocale peut être bloquée par certains navigateurs tant que l'utilisateur n'a pas interagi avec la page.


## Jingle de la Draft (V1.2)

Dans la fenêtre de sélection, le bouton « Lancer le jingle NBA » ouvre le lecteur intégré YouTube pour https://www.youtube.com/watch?v=DbI3rwEncQE. La vidéo reste hébergée par YouTube : aucun fichier audio protégé n’est inclus. La lecture automatique, le son, les publicités et la disponibilité dépendent du navigateur et de YouTube. La voix de synthèse est distincte ; il n’est pas possible de baisser automatiquement le volume du lecteur YouTube pendant l’annonce. Fermer la fenêtre ou cliquer « Arrêter » stoppe le lecteur.
