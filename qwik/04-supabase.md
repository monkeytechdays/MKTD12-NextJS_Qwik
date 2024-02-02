# Supabase

Supabase est une alternative open-source à Firebase, nous allons l'utiliser pour charger les articles de notre blog.

Voir la documentation ici : https://qwik.dev/docs/integrations/supabase/

Pour récupérer un article, vous pouvez procéder de cette façon :

```ts
await supabaseClient.from('posts').select().eq('id', requestEv.params.id).single();
```

## Exercice

Modifiez vos loaders pour utiliser Supabase pour charger les articles.

## Aller plus loin

Vous pouvez générer un fichier de type avec Supabase pour directement avoir les types des données retournées par l'API.

1. Utilisez la cli de Supabase `[npx/pnpx/yarn dlx/bunx] supabase login`.
1. Générez le fichier de type avec `[npx/pnpx/yarn dlx/bunx] supabase gen types typescript --project-id [project_id] > supabase.type.ts`.
1. Dans le `routeLoader$`, passez le type généré au client : `createServerClient<Database>(...)`

## Solution

Voir [ici](./solution/04-supabase.md)
