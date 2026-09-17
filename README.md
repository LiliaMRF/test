# Site de Lilia Marouf — déploiement GitHub Pages

Ce dossier contient tout ce qu'il faut pour mettre le site en ligne gratuitement avec GitHub Pages.

## Contenu du dossier

- `index.html` — le site complet (une seule page, tout est inclus : HTML, CSS, JS)
- `robots.txt` — autorise les moteurs de recherche à indexer le site
- `sitemap.xml` — liste des pages pour les moteurs de recherche
- `.nojekyll` — désactive le traitement Jekyll de GitHub (fichier vide, à garder tel quel)

## Étapes de mise en ligne

1. **Créer un dépôt GitHub**
   - Sur github.com, cliquez sur *New repository*.
   - Nommez-le par exemple `lilia-marouf-site` (le nom n'a pas d'importance).
   - Laissez-le public, sans README ni licence à l'initialisation.

2. **Envoyer les fichiers**
   - Sur la page du dépôt vide, cliquez sur *uploading an existing file*.
   - Glissez-déposez les 4 fichiers de ce dossier (`index.html`, `robots.txt`, `sitemap.xml`, `.nojekyll`).
   - Validez le commit (*Commit changes*).

   Ou en ligne de commande, depuis ce dossier :
   ```
   git init
   git add .
   git commit -m "Premier déploiement du site"
   git branch -M main
   git remote add origin https://github.com/VOTRE-COMPTE/lilia-marouf-site.git
   git push -u origin main
   ```

3. **Activer GitHub Pages**
   - Dans le dépôt : *Settings* → *Pages* (menu de gauche).
   - Sous *Build and deployment*, choisissez la source **Deploy from a branch**.
   - Branche : `main`, dossier : `/ (root)`. Enregistrez.
   - Après une à deux minutes, le site sera visible à l'adresse :
     `https://VOTRE-COMPTE.github.io/lilia-marouf-site/`

4. **(Optionnel) Nom de domaine personnalisé**
   - Si vous avez un domaine (ex. `liliamarouf.fr`), ajoutez-le dans *Settings → Pages → Custom domain*.
   - Chez votre registrar, créez un enregistrement CNAME pointant vers `VOTRE-COMPTE.github.io`.
   - GitHub crée alors automatiquement un fichier `CNAME` dans le dépôt — ne le supprimez pas.

## À personnaliser avant la mise en ligne réelle

Le site fonctionne tel quel, mais certains éléments sont volontairement laissés en placeholder :

- **Coordonnées de contact** (page Contact) : e-mail, téléphone, zone d'intervention.
- **Adresse e-mail du formulaire** : dans `index.html`, cherchez `contact@a-personnaliser.fr` et remplacez-la par votre vraie adresse (le formulaire ouvre la messagerie du visiteur avec le message pré-rempli — il n'y a pas de serveur d'envoi).
- **Mentions légales / confidentialité** : statut juridique, SIRET, adresse, nom de l'hébergeur.
- **Nom de domaine** : dans `index.html` (balises `canonical` et `og:`), ainsi que dans `robots.txt` et `sitemap.xml`, remplacez `https://www.liliamarouf.fr` par votre domaine réel une fois choisi.
- **Réalisations** : les trois exemples sont des gabarits à remplacer par de vrais projets au fur et à mesure.

## Notes techniques

- Le site est une page unique avec un routeur en JavaScript (les URLs `#/services`, `#/contact`, etc. changent le contenu affiché sans recharger la page). C'est rapide et simple à héberger, mais Google indexera surtout la page d'accueil : pour un référencement multi-pages plus poussé, il faudra à terme des URLs distinctes par page.
- Aucune dépendance externe à installer : le site fonctionne dès qu'il est en ligne, sans build ni serveur particulier.
