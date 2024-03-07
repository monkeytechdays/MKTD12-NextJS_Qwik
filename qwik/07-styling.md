# Styling

Voir la documentation ici : https://qwik.dev/docs/components/styles/

## Exercice

Il n'y a pas d'exercice en particulier pour cette section. Vous être libre de styliser votre application comme vous le souhaitez. Essayez d'utiliser les différentes méthodes de stylisation pour vous familiariser avec chacune.

## Note

Si vous ne savez pas quelle méthode choisir, voici quelques infos :

- CSS Modules : Pas très pratique à utiliser (il n'y a pas d'auto-complétion dans les composants, et pas de vérification au build si la classe existe).
- CSS-in-JS : L'intégration avec Qwik est optimale avec styled-vanilla-extract, c'est une bonne solution avec Qwik si vous aimez le CSS-in-JS
- useStylesScoped$: Probablement la solution la plus proche du CSS classique, avec un peu de magie qui permet d'isoler le css au composant (scoping). (Similaire au système d'Angular).
- Tailwind (ou équivalent): Si vous aimez les utility-first, c'est une bonne solution.

Personnellement, je préfère utiliser Tailwind (qui fonctionne de la même manière sur tout les frameworks).

Voir https://qwik.dev/docs/integrations/tailwind/
