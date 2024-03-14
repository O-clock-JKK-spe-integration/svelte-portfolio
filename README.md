# Installer un nouveau template Svelte, le routeur et initialiser Git

## Marche à suivre

cette commande crée un dossier "svelte-portfolio" dans lequel elle va préparer Svelte
Nous pouvons choisir un autre nom pour notre dossier, à notre convenace. Ce sera ce dossier que nous transmettrons sur GitHub.
`npm create vite@latest svelte-portfolio -- --template svelte -y`

`cd svelte-portfolio`

`npm install`

`npm install svelte-spa-router@~3.3.0`
(en attendant une version 4 stable du router, on bloque sur des versions en dessous grace au tilde (~) avant le numéro de version.)

Ici, très important, on initialise Git en prévision du déploiement depuis le repo GitHub
Créer un fichier `README.md` à la racine du projet puis :
`git init && git add -A && git commit -m "Initial commit"`

Rennommez votre branche master en main pour correspondre au nouveau standard Github :
`git branch -m master main`

Puis on lance le serveur de dev avec vite (pour info, on appelle un script depuis package.json)
`npm run dev`

Puis on nettoie le code par défaut du template avant de commencer :
vider `App.svelte` et `app.css`, supprimer `Counter.svelte` dans le dossier `lib`

Nous avons besoin d'un reset pour nos css, afin d'harmoniser le rendu entre les navigateurs (on a choisi `normalize.css` mais il en existe d'autres)
on l'appellera depuis `main.js`, en première position.

Vos styles vont soit dans dans `app.css` pour le global, ou bien directement dans un composant svelte entre les balises `<style></style>`, les styles sont alors appliqués uniquement au composant qui les embarque (Sur le Web : "svelte scoped css" pour approfondir la question)

# Développement du projet

Après la séquence de développement en local, votre projet est pret à etre déployé et vous faites un commit :

`git add .`

`git commit -m "un message de commit signifiant"`

Puis vous passez à l'étape suivante.

# Déploiement et mises à jour

## Marche à suivre

Il faut d'abord créer le dépot Github sur lequel on va pusher notre projet local, pour bénéficier de l'offre gratuite d'hébergement, il devra impérativement etre "Public".

_NB : C'est pour cette raison que vous ne pourrez pas déployer un projet depuis le depot de la spé, tous étant "privés" par défaut._

Créer un nouveau repo github depuis votre compte ave le bouton vert en haut à droite "New" :
**choisir votre propre compte comme "Owner"**, **puis nommer le nouveau repo comme votre repo local**, choisissez aussi le statut **"Public"**, puis valider sans rien changer d'autres ("Create new repository")

Maintenant, dans votre projet, à la racine, ouvrez un terminal et validez les commandes git suivantes qui vont relier votre dépot local au repo nouvellement créé :

`git remote add origin le-ssh-de-votre-nouveau-depot-vide`

Exemple de commande : `git remote add origin git@github.com:Mellifico/svelte-portfolio.git`

Puis un premier push qui fait le lien entre les branches locale et distante :

`git push -u origin main`

Retourner sur Github voir votre dépot, rafraichissez la page si besoin, et vérifier qu'il contient bien maintenant votre projet.

### Déployer sur Vercel

SignUp sur [Vercel](https://vercel.com/) avec votre compte Github

Menu _"Add New"_ en haut à droite > _"Project"_

Puis depuis la liste que vous présente l'interface repérez votre nouveau repo et cliquer _"import"_

Puis sur la page du projet, choisissez un nom qui servira dans l'url du sous-domaine gratuit fourni par Vercel. Votre site sera disponible à l'url :

**votre-projet.vercel.app**

Il sera probablement nécessaire par la suite d'acheter un nom de domaine (15€/mois) pour changer l'url gratuite, à moins que vous ne publiiez un projet pour votre portfolio, ou bien pour d'autres raisons qui ne nécessite pas de domaine particulier.

Une fois le nom choisi, ne changez rien d'autre et cliquer "Deploy" en bas.
Vercel va alors faire toutes les opérations nécessaires automatiquement et déployer votre site. Vous serez amené à une page avec une capture d'écran de votre site que vous pourrez cliquer pour vous rendre sur l'url. Le site fait maintenant partie de votre "dashboard".

# Pour mettre à jour le code de votre site sur le Web (CI/CD):

Faites vos modifications en local, puis :

`git add .`

`git commit -m "message"`

`git push`

Vercel va alors mettre à jour votre site automatiquement, car il détecte vos push.

Et voilà.
