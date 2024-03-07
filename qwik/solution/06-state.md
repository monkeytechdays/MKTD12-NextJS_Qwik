# State

Voici un exemple de composant Slideshow basique

`./src/components/slideshow/slideshow.tsx`

```tsx
import { $, component$, useSignal, useVisibleTask$ } from '@builder.io/qwik';

export interface SlideshowProps {
  imgs: string[];
}

export const Slideshow = component$<SlideshowProps>((props) => {
  const currentImgIdx = useSignal(0);

  const changeImgIdx = $((val: number) => {
    currentImgIdx.value += val;
    if (currentImgIdx.value < 0) {
      currentImgIdx.value = props.imgs.length - 1;
    } else if (currentImgIdx.value >= props.imgs.length) {
      currentImgIdx.value = 0;
    }
  });

  const onButtonClick = $((evt: PointerEvent) => {
    const button = evt.target as HTMLButtonElement;
    changeImgIdx(+button.dataset.val!);
  });

  useVisibleTask$(() => {
    const interval = setInterval(() => changeImgIdx(1), 5000);
    return () => clearInterval(interval);
  });

  return (
    <div>
      <img src={props.imgs[currentImgIdx.value]} height={200} width={350} />
      <div>
        <button type="button" data-val="-1" onClick$={onButtonClick}>
          Previous
        </button>
        <button type="button" data-val="1" onClick$={onButtonClick}>
          Next
        </button>
      </div>
    </div>
  );
});
```
