# SEO

Voici un exemple de génération de balises meta pour le SEO.

`./src/routes/blog/[id]/index.tsx`

```tsx
[...]

export const head: DocumentHead = ({ resolveValue }) => {
  const post = resolveValue(usePost);
  if (!post) {
    return {};
  }
  const meta = [
    {
      property: 'og:type',
      content: 'article',
    },
    {
      property: 'og:title',
      content: post.title,
    },
    {
      property: 'og:description',
      content: post.abstract,
    },
    {
      property: 'article:author',
      content: post.author,
    },
    {
      property: 'article:published_time',
      content: post.created_at,
    },
  ];
  if (post.thumbnail) {
    meta.push({
      property: 'og:image',
      content: post.thumbnail,
    });
  }
  return {
    title: post.title,
    meta,
  };
};
```

`./src/routes/layout.tsx`

```tsx
[...]

export const head: DocumentHead = ({ head }) => {
  let title = '';
  if (head.title) {
    title = `${head.title} | `;
  }
  return {
    title: title + 'My conference',
  };
};
```
