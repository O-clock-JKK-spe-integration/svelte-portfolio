# Installer un nouveau template Svelte, le routeur et initialiser Git

## Une série de commandes pour commencer :

cette commande crée un dossier "svelte-portfolio" dans lequel elle va préparer Svelte
Nous pouvons choisir un autre nom pour notre dossier, à notre convenace. Ce sera ce dossier que nous transmettrons sur GitHub
`npm create vite@latest svelte-portfolio -- --template svelte -y`

`cd svelte-portfolio`

`npm install`
en attendant une version 4 stable du router, on bloque sur des versions en dessous grace au tilde (~) avant le numéro de version.

`npm install svelte-spa-router@~3.3.0`

Ici, très important, on initialise Git en prévision du déploiement (déploiement d'après le repo GitHub)
`git init && git add -A && git commit -m "Initial commit"`

Puis on lance le serveur de dev avec vite (on appelle un script depuis package.json)
`npm run dev`

Puis on nettoie le code par défaut du template avant de commencer : 
vider `App.svelte` et `app.css`, supprimer `Counter.svelte` dans le dossier `lib`

Nous avons besoin d'un reset pour nos css, afin d'harmoniser le rendu entre les navigateurs (on a choisi `normalize.css` mais il en existe d'autres) 
on l'appellera depuis `main.js`, en première position.

Vos styles vont dans app.css, ou bien en interne dans un composant svelte entre les balises `<style>...</style>`, les styles sont alors appliqués uniquement au composant qui les embarque (Sur le Web : "svelte scoped css" pour approfondir la question)

## C'est à vous de jouer maintenant, créez votre site !


# Déploiement et mises à jour

Push du repo local sur github

Le repo doit etre "public"

Relier votre compte Vercel à votre compte github

Choisissez depuis Vercel le repo à déployer

choisir son domaine, par exemple votrenom.vercel.app, ou bien configurer un nom de domaine de premier niveau que vous pouvez acquérir pour 15e/an environ

Déployez !