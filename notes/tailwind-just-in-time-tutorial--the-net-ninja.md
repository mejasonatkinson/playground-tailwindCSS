#  [Tailwind Just in Time Tutorial - The Net Ninja](https://www.youtube.com/playlist?list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ)

## [Tailwind Just in Time Tutorial #1 - Introduction - The Net Ninja](https://www.youtube.com/watch?v=aQS7kaje-24&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=2)

Just in Time (JIT)

Designed for a better Developer experience.

VS Code extension: Live server

Open with live server

index.html

`node -v`

need to be higher than 12.13

tailwind cli

`npx tailwindcss -o ./build/styles.css`

`-o` for output destination.

This will give the full stylesheet.

index.html

`<link rel="stylesheet" href="/build/styles.css">`

```
<div class="p-8 text-center">
    <h1 class="text-4xl text-blue-600 font-bold">Tailwind JIT Tutorial</h1>
    <h2 class="text-2xl text-gray-500 font-semibold">(Just in Time)</h2>
</div>
```

styles.css = 4mb!!


src/styles.css

```
@tailwind base;
@tailwind components;
@tailwind utilities;

.testing {
    background: #f2f2f2;
    border:2px solid #777;
}
```

`npx tailwindcss -i ./src/styles.css -o ./build/styles.css`

`-i` input destinations.

## [Tailwind Just in Time Tutorial #2 - Using the Just in Time Compiler - The Net Ninja](https://www.youtube.com/watch?v=mP2TPWZRSmk&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=3)

## [Tailwind Just in Time Tutorial #3 - Extra Variants - The Net Ninja](https://www.youtube.com/watch?v=DduPHtznQ2o&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=4)

## [Tailwind Just in Time Tutorial #4 - Arbitrary Values - The Net Ninja](https://www.youtube.com/watch?v=4gEH1h5C-Tc&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=5)

## [Tailwind Just in Time Tutorial #5 - Tailwind JIT with Next.js - The Net Ninja](https://www.youtube.com/watch?v=D3Kz2bOQR5E&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=6)