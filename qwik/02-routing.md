# Routing

La documentation du routing est disponible ici :

https://qwik.dev/docs/routing/

Pour le layout vous aurez aussi besoin de la documentation suivante :

https://qwik.dev/docs/layout/

## Exercice

Créez deux pages supplémentaires : une page "/blog" et une page "/contact".

Ajoutez un menu de navigation dans le layout pour naviguer entre les différentes pages. (voir `layout.tsx` et `<Link>`)

Ajoutez une page dynamique "/blog/[id]" qui affiche le paramètre "id" dans la page. (voir `[paramName]` et `useLocation()`)

## Bonus

Vous pouvez utiliser la commande `[pnpm/npx/yarn] qwik new /blog` pour créer une page "/blog" plus rapidement.

Si vous êtes sur VSCode, le starter kit intègre directement des snippets pour Qwik. Par exemple, essayez de taper "qpage" dans un fichier .tsx et appuyez sur la touche "Tab" pour générer un composant Qwik 🪄.

## Aller plus loin

https://qwik.dev/docs/advanced/routing/ (La partie sur les layout groupée pourrais être utile pour cet après midi)

Pour un meilleur rendu du menu de navigation, vous pouvez créer un composant NavLink : https://qwik.dev/docs/cookbook/nav-link/
