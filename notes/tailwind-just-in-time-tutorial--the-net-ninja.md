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

`npx tailwindcss -i ./src/styles.css -o ./build/styles.css --JIT --purge="./*.html"`

```
<div class="p-8 text-center">
    <button class="bg-blue-600 text-white p-2 rounded">Click me</button>
    <button class="">Click me</button>
</div>
```

New styling will not appear...

`npx tailwindcss -i ./src/styles.css -o ./build/styles.css --JIT --purge="./*.html" --watch`

Will watch for changes

```
<div class="p-8 text-center">
    <button class="bg-blue-600 text-white p-2 rounded">Click me</button>
    <button class="bg-green-500 text-white p-2 rounded">Click me</button>
</div>
```

New styling will appear!

`npx tailwindcss init`

tailwind.config.js

```
module.exports = {
    mode: 'jit',
    purge: ['./*.html']
}
```

`npx tailwindcss -i ./src/styles.css -o ./build/styles.css --watch`
 Will now do this, do the same thing.

## [Tailwind Just in Time Tutorial #3 - Extra Variants - The Net Ninja](https://www.youtube.com/watch?v=DduPHtznQ2o&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=4)


```
<div>
    <h3 class="first-letter:font-bold first-letter:text-green-500">Todos:</h3>
    <ul class="my-4 list-disc marker:text-blue-600">
        <li class="marker:text-green-500">Get out of bed</li>
        <li class="selection:bg-pink-500">Play Mario Kart</li>
        <li class="selection:bg-purple-500">Do some work</li>
    </ul>
    <p class="first-line:font-semibold"> 
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus et convallis nunc. Phasellus efficitur nibh non erat pharetra, vitae fermentum odio accumsan. Phasellus maximus urna accumsan nulla placerat, nec varius magna pulvinar. Phasellus eget euismod neque, at elementum eros. Donec sed nibh urna. Ut ac augue diam. Maecenas turpis erat, sodales vitae lorem nec, volutpat gravida quam. Interdum et malesuada fames ac ante ipsum primis in faucibus. Cras rhoncus diam eget ipsum facilisis, vel lacinia arcu ullamcorper. Pellentesque eros nibh, pharetra quis nunc sed, ornare pretium enim. Etiam a auctor tellus.Quisque imperdiet mi nec purus faucibus ultricies. Donec ipsum ligula, pretium quis bibendum nec, volutpat id felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec nec varius risus. Etiam molestie vitae ante quis venenatis. Etiam hendrerit velit nec turpis porttitor aliquam.
    </p>
</div>
```

## [Tailwind Just in Time Tutorial #4 - Arbitrary Values - The Net Ninja](https://www.youtube.com/watch?v=4gEH1h5C-Tc&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=5)

## [Tailwind Just in Time Tutorial #5 - Tailwind JIT with Next.js - The Net Ninja](https://www.youtube.com/watch?v=D3Kz2bOQR5E&list=PL4cUxeGkcC9ht1OMQPhBVKAb2dVLhg-MJ&index=6)