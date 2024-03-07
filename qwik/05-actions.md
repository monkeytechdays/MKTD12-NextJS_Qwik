# Actions

Voir la documentation ici : https://qwik.dev/docs/action/

Pour récupérer les commentaires avec supabase, vous pouvez procéder de cette façon :

```typescript
const { data } = await supabaseClient
  .from('BlogPostComment')
  .select()
  .eq('blogPostId', blogPostId)
  .order('created_at', { ascending: false });
```

Pour ajouter un commentaire, vous pouvez procéder de cette façon :

```typescript
await supabaseClient.from('BlogPostComment').insert({ blogPostId, content });
```

## Exercice

Ajouter un formulaire de commentaire (simple input text avec bouton submit) sur la page "/blog/[id]".

Utilisez `zod$()` pour s'assurer que le commentaire n'est pas vide.

La liste des commentaires doit s'afficher au dessus du formulaire.

## Note

Vous n'avez pas besoin d'explicitement recharger la liste des commentaires, puisqu'une `routeAction$` va recharger toute la page (coté serveur), donc relancer les `routeLoader$`. Si javascript est activé, Qwik va remplacer les données directement la page, sinon le formulaire recharge la page entière comme un formulaire HTML classique.

Comme tout les frameworks, Qwik nous protège contre les attaques XSS (Cross Site Scripting) en échappant les données par défaut.

Vous avez probablement envie de vider le formulaire après avoir soumis le commentaire. Pour cela, rendez-vous à l'exercice suivant : [State](./06-state.md)

## Aller plus loin

Vous pouvez ajouter un système simple de captcha (une question basique). Il vous faudra créer un `routeLoader$` (note: il n'y a pas de limite de `routeLoader$` par page) pour générer la question et vérifier la réponse avec un validateur (https://qwik.dev/docs/validator/) dans le `routeAction$`.
