# State

Voir la documentation ici : https://qwik.dev/docs/components/state/

## Exercice

Sur le formulaire de commentaire, vous pouvez maintenant vider le champ texte après avoir soumis le commentaire. Vous aurez besoin d'avoir une référence à l'élément input : `const commentInput = useSignal<HTMLInputElement>();` et de l'attribuer à l'élément input : `<input ref={commentInput} />`. Vous pouvez ensuite vider le champ texte avec `commentInput.value.value = '';`.
Vous pouvez utiliser `useTask$` pour le déclenchement de ce code.

Créez un composant qui prend en entrée une liste de liens d'images (https://qwik.dev/docs/components/overview/#props) et qui affiche une image à la fois. Ajoutez deux boutons pour naviguer entre les images (https://qwik.dev/docs/components/events/)

Exemple d'utilisation :

```
<Slideshow
  imgs={[
    'https://fakeimg.pl/350x200/?text=Hello',
    'https://fakeimg.pl/350x200/?text=World',
    'https://fakeimg.pl/350x200/?text=🌎',
  ]}
/>
```

Le composant sera stocké dans src/components/slideshow.tsx.

Ajoutez un minuteur pour changer d'image automatiquement toutes les 5 secondes (avec `useVisibleTask$`)

Vous pouvez afficher ce composant directement sur la page d'accueil.

## Bonus

Vous pouvez aussi créer un composant avec `[pnpm/npx/yarn] qwik new`.
