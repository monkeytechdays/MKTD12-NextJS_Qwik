# Wording

## SPA

Une single page application (SPA) fonctionne en rendant et en récupérant les données directement dans le navigateur. Cela entraîne un temps de chargement plus long pour le First Contentful Paint (FCP), ce qui affecte l'expérience utilisateur. Mais une fois que le bundle JavaScript est téléchargé, l'application devient interactive et les utilisateurs peuvent naviguer entre les pages sans avoir à recharger la page.

## MPA

Une application multi-page (MPA) est une application web traditionnelle qui recharge la page entière et affiche le nouveau document HTML à chaque fois qu'un utilisateur interagit avec l'application. Chaque page de l'application est associée à sa propre URL. Les MPA sont généralement plus simples à mettre en œuvre car elles reposent sur des approches de développement web standard. Cependant, elles peuvent offrir une expérience utilisateur moins fluide que les applications à page unique (SPA), car elles nécessitent un rechargement complet de la page pour chaque navigation.

## SSR

Le Server side rendering (SSR) atténue ces problèmes en générant la page initiale sur le serveur même, réduisant ainsi le temps nécessaire pour le FCP et améliorant considérablement l'expérience utilisateur. Cependant, la page ne deviendra pas immédiatement interactive et le navigateur devra attendre qu'il ait terminé le téléchargement du bundle JavaScript pour ajouter de l'interactivité.... Sauf avec Qwik, qui n'a pas besoin de cette étape 🔮.

## SSG

Le Static site generation (SSG) est une technique qui consiste à générer des pages HTML à l'avance, au moment de la construction de l'application. Cela permet de réduire le temps de chargement initial, mais cela signifie que les données ne sont pas à jour. C'est pourquoi les SSG sont généralement utilisés pour les sites web statiques, comme les blogs, les sites de documentation, etc...

## Et Qwik dans tout ça ?

Qwik permet de combiner les avantages du SSR et du SSG, sans leurs inconvénients. Il permet de générer des pages HTML à l'avance, ou à la demande, et de les rendre immédiatement interactives. Cela permet d'obtenir un temps de chargement initial rapide, une interaction utilisateur immédiate et une facilité d'adoption pour les développeurs.
Avec Qwik la distinction entre SPA et MPA disparait, toute les applications peuvent être à la fois SPA et MPA en même temps. Le choix n'est plus une décision d'architecture déterminée au début du projet, mais cette décision peut être prise pour chaque lien.
