# Installer un nouveau template Svelte, le routeur et initialiser Git

## Une série de commandes pour commencer :

cette commande crée un dossier "svelte-portfolio" dans lequel elle va préparer Svelte
Nous pouvons choisir un autre nom pour notre dossier, à notre convenace. Ce sera ce dossier que nous transmettrons sur GitHub
`npm create vite@latest svelte-portfolio -- --template svelte -y`

`cd svelte-portfolio`

`npm install`
en attendant une version 4 stable du router, on bloque sur des versions en dessous grace au tilde (~) avant le numéro de version.

`npm install svelte-spa-router@~3.3.0`

Ici, très important, on initialise Git en prévision du déploiement (déploiement depuis le repo GitHub)
Créer un fichier `README.md` à la racine du projet
`git init && git add -A && git commit -m "Initial commit"`

Puis on lance le serveur de dev avec vite (pour info, on appelle un script depuis package.json)
`npm run dev`

Puis on nettoie le code par défaut du template avant de commencer :
vider `App.svelte` et `app.css`, supprimer `Counter.svelte` dans le dossier `lib`

Nous avons besoin d'un reset pour nos css, afin d'harmoniser le rendu entre les navigateurs (on a choisi `normalize.css` mais il en existe d'autres)
on l'appellera depuis `main.js`, en première position.

Vos styles vont soit dans dans `app.css`, ou bien en interne dans un composant svelte entre les balises `<style></style>`, les styles sont alors appliqués uniquement au composant qui les embarque (Sur le Web : "svelte scoped css" pour approfondir la question)

## Développement du projet

Après la séquence de développement en local, votre projet est pret à etre déployé et vous faites un commit :
`git add .`
`git commit -m "un message de commit signifiant"`

 Puis vous passez à l'étape suivante.

# Déploiement et mises à jour

Il faut d'abord créer le dépot Github sur lequel on va pusher notre projet local, pour bénéficier de l'offre gratuite d'hébergement, il devra impérativement etre "Public".

NB : C'est pour cette raison que vous ne pourrez pas déployer un projet depuis le depot de la spé, tous étant "privés" par défaut.

Créer un nouveau repo github depuis votre compte ave le bouton vert en haut à droite "New" : 
choisir votre propre nom comme "Owner", puis le nommer comme votre repo local, choisissez le statut "Public", valider **sans rien changer** d'autres ("Create new repository")



Puis dans votre projet, à la racine, ouvrez un terminal et validez les commandes git suivantes qui vont relier votre dépot local au repo nouvellement créé :

`git remote add origin le-ssh-de-votre-nouveau-depot-vide`

Exemple de commande : `git remote add origin git@github.com:Mellifico/svelte-portfolio.git`

Maintenant, nommez bien votre branche principale locale comme celle du nouveau repo.
NB : selon les nouvelles conventions Github, la branche principale d'un nouveau repo est maintenant "main" par défaut.

`git branch -M main`

Puis un premier push avec le lien entre les branches :

`git push -u origin main`




Relier votre compte Vercel à votre compte github




Choisir depuis Vercel le repo à déployer

Déployez !

## Que faire après

choisir son domaine, par exemple votrenom.vercel.app, ou bien configurer un nom de domaine de premier niveau que vous pouvez acquérir pour 15e/an environ
