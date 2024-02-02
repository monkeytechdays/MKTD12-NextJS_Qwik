# Actions

Voir la documentation ici : https://qwik.dev/docs/action/

## Exercice

Ajouter un formulaire de commentaire (simple input text avec bouton submit) sur la page "/blog/[id]".

Utilisez `zod$()` pour s'assurer que le commentaire n'est pas vide.

La liste des commentaires dois s'afficher en dessous du formulaire.

## Aller plus loin

Vous pouvez ajouter un système simple de captcha (un question/réponse). Il vous faudra créer un `routeLoader$` (note: il n'y a pas de limite de `routeLoader$` par page) pour générer la question et vérifier la réponse avec un validateur (https://qwik.dev/docs/validator/) dans le `routeAction$`.
