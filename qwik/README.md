# MKTD12 - Qwik

Bienvenue dans le module Qwik du MonkeyTechDay #12, je suis Guillaume d'Eimar de Jabrun et je vous souhaite une bonne découverte !

## Qwik ?

Qwik est un framework conçu pour améliorer les performances de chargement des applications web. Créé par Misko Hevery, l'auteur de Angular (& AngularJS), Qwik a été introduit en 2022 avec l'objectif de fournir un temps de chargement initial rapide, une interaction utilisateur immédiate et une facilité d'adoption pour les développeurs.

Après avoir été annoncé pour la première fois en 2022, il donc encore très peu utilisé en production, mais il a atteint sa version 1.0 en Mai 2023.

Qwik est volontairement très ressemblant à React, mais il y a quelques différences importantes :

## "Resumable"

Qwik est "resumable", c'est à dire qu'il peut reprendre le rendu d'une page à partir d'un état précédent. Cela permet de réduire le temps de chargement initial, et de fournir une expérience utilisateur plus rapide.

Le meilleur moyen d'expliquer la "resumability" est de comprendre comment la génération actuelle de frameworks functionne ("hydratation").

Quand un application démarre sur un client, elle a besoin que le framework sur le client restaure trois informations :

- Listeners - localiser les écouteurs d'événements et les installer sur les nœuds DOM pour rendre l'application interactive.
- Arbre de composants - construire une structure de données interne représentant l'arbre des composants de l'application.
- État de l'application - restaurer toutes les données qui ont été récupérées ou enregistrées dans un store sur le serveur.

C'est un processus qui peut prendre du temps. Qwik permet de réduire ce temps en permettant de reprendre le rendu à partir d'un état précédent, et donc complètement éviter la phase de "hydratation".

![Hydration vs Resumability](https://cdn.builder.io/api/v1/image/assets%2FYJIGb4i01jvw0SRdL5Bt%2Fa6d8c3bacc3c4cf88446e41a71cda21c)

## Signaux

Un autre aspect de Qwik contraitement à React, est qu'il utilise les signaux pour la gestion de l'état. C'est un concept de plus en plus utilisé dans les frameworks front-end moderne comme SolidJS, Angular (>=v16), Svelte (>=5), etc...

## Qwik City

Tout comme React, Qwik se concentre sur l'API de composant. Qwik City apporte notament à Qwik un routeur et un serveur. Qwik City est à Qwik, ce que Next.js est à React, ce que Nuxt est à Vue, SvelteKit à Svelte, Analog à Angular, etc...

## Liste des exercices :

- [Hello world](./01-hello-world.md)
- [Routing](./02-routing.md)
- [Route loaders](./03-loaders.md)
- [Supabase](./04-supabase.md)
- [Actions](./05-actions.md)
- [State](./06-state.md)
- [Styling](./07-styling.md)
- [SEO](./08-seo.md)
