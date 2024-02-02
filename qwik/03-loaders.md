# Route loaders

La documentation des route loaders est disponible ici :

https://qwik.dev/docs/route-loader/

Pour le rendu des articles, vous aurez aussi besoin de la documentation suivante :

https://qwik.dev/docs/components/rendering/

## Exercice

A l'aide de l'API https://jsonplaceholder.typicode.com/posts affichez la liste des articles sur la page "/blog".

Voici l'interface des posts retourné par l'API :

```ts
interface Post {
  userId: number;
  id: number;
  title: string;
  body: string;
}
```

Dans un second temps, dans la page "/blog/[id]" affichez le contenu de l'article correspondant à l'id. Dans le cas où l'article n'existe pas, le status de la page dois être 404 et dois afficher un message d'erreur.

Pour finir, ajoutez un lien sur les articles de la page "/blog" pour accéder à la page "/blog/[id]".

## Bonus

Sur VSCode, le snippet "qloader$" permet de générer un route loader.

## Aller plus loin

Remaniez le code pour déplacer les loaders dans un autre fichier. De cette manière vous pouvez centraliser le code de chargement des données. Voir https://qwik.dev/docs/cookbook/re-exporting-loaders/
