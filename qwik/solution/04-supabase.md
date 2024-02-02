# Supabase

Voici un exemple de ce que vous devez avoir pour charger les articles de votre blog avec Supabase.

`./src/shared/post/loaders.ts`

```ts
/_ eslint-disable qwik/loader-location _/
import { routeLoader$, type RequestEventLoader } from '@builder.io/qwik-city';
import { createServerClient } from 'supabase-auth-helpers-qwik';
import type { Database } from '../supabase.type';

function createClient(requestEv: RequestEventLoader) {
  return createServerClient<Database>(
    requestEv.env.get('PUBLIC_SUPABASE_URL')!,
    requestEv.env.get('PUBLIC_SUPABASE_ANON_KEY')!,
    requestEv
  );
}

export const usePosts = routeLoader$(async (requestEv) => {
  const client = createClient(requestEv);
  const { data } = await client.from('posts').select();
  return data!;
});

export const usePost = routeLoader$(async (requestEv) => {
  const client = createClient(requestEv);
  const { data } = await client.from('posts').select().eq('id', requestEv.params.id).single();
  if (!data) {
    requestEv.status(404);
    return;
  }
  return data;
});
```
