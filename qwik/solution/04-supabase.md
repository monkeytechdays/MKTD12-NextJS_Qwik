# Supabase

Voici un exemple de ce que vous pouvez avoir pour charger les articles de votre blog avec Supabase.

`./src/data-access/supabase.ts`

```typescript
import type { RequestEventLoader } from '@builder.io/qwik-city';
import { createServerClient } from 'supabase-auth-helpers-qwik';
import type { Database } from './supabase.type';

export function createSupabaseClient(requestEv: RequestEventBase) {
  return createServerClient<Database>(
    requestEv.env.get('PUBLIC_SUPABASE_URL')!,
    requestEv.env.get('PUBLIC_SUPABASE_ANON_KEY')!,
    requestEv
  );
}
```

`./src/data-access/post.ts`

```typescript
import { type SupabaseClient } from 'supabase-auth-helpers-qwik';
import type { Database } from './supabase.type';

export async function fetchPosts(client: SupabaseClient<Database>) {
  const { data } = await client.from('posts').select();
  return data!;
}

export async function fetchPost(client: SupabaseClient<Database>, id: number) {
  const { data } = await client.from('posts').select().eq('id', id).single();
  return data;
}
```

`./src/routes/blog/[id]/index.tsx`

```tsx
import { component$ } from '@builder.io/qwik';
import { routeLoader$ } from '@builder.io/qwik-city';
import { createSupabaseClient } from '~/shared/data-access/supabase';
import { fetchPost } from '../../../shared/data-access/post';

export const usePost = routeLoader$(async (requestEv) => {
  const data = await fetchPost(createSupabaseClient(requestEv), Number(requestEv.params.id));
  if (!data) {
    requestEv.status(404);
    return null;
  }
  return data;
});

export default component$(() => {
  const post = usePost();
  if (!post.value) {
    return <div>Post not found...</div>;
  }
  const formattedDate = new Date(post.value.created_at).toLocaleDateString('en-US', {
    year: 'numeric',
    month: 'long',
    day: 'numeric',
  });
  return (
    <article>
      <header>
        <time dateTime={post.value.created_at}>{formattedDate}</time>
        <h1>{post.value.title}</h1>
        {post.value.thumbnail && <img src={post.value.thumbnail} alt="" width={250} height={140} loading="lazy" />}
      </header>
      <p>{post.value.body}</p>
    </article>
  );
});
```
