# [Tailwind CSS Tutorial - The Net Ninja](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw)

## [Tailwind CSS Tutorial #1 - Intro & Setup](https://www.youtube.com/watch?v=bxmDnn7lrnk&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw)

What is tailwind CSS

CSS framework

Much lower-level than Bootstrap, Materialize etc

`class="rounded shadow p-2 bg-white"`

You Should Know...
- Both HTML & CSS

Using Tailwind CSS
- Install Tailwind using npm
- You'll need node.js installed on your computer

`node -v`

`cd documents`
`cd tuts`
`mkdir ninjafood`
`cd ninkafood`
`code .` (using vs code)

New Terminal

`npm init -y`

package.json

`npm install tailwindcss`

How Tailwind Works

styles.css (src) -> Tailwind -> styles.css (public)

create `/public`
create `/src`
create `/src/styles.css`
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

`package.json`
```
"scripts": {
    "build-css": "tailwindcss build src/styles.css -o public/styles.css"
},
```

`npm run build-css`

https://github.com/iamshaunjp/tailwind-tutorial

## [Tailwind CSS Tutorial #2 - HTML Template](https://www.youtube.com/watch?v=3ZMUgga6SsY&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=2)

`public/index.html`

```
<link rel="stylesheet" href="styles.css">

<div> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1>
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li>
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main>
        <div>
            <a href="#">Log in</a>
            <a href="#">Sign up</a>
        </div>
        <header>
            <h2>Recipes</h2>
            <h3>For Ninjas</h3>
        </header>
        <div>
            <h4>Latest Recipes</h4>

            <div>
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4>Most Popular</h4>

            <div>
                <!-- cards go here -->
            </div>

            <div>
                <div>Load more</div>
            </div>
        </div>
    </main>
</div>
```

`npm install live-server -g`

`live-server public`

`public/img/...` add images

## [Tailwind CSS Tutorial #3 - Fonts & Colors](https://www.youtube.com/watch?v=w0KZhi3DD-0&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=3)

`public/index.html`

https://tailwindcss.com/docs/installation

https://tailwindcss.com/docs/font-family

text & colours:

---

`class="text-yellow-400"`
`class="text-red-700"`
`class="text-gray-600"`

`text-colour-strength`

---

`text-xl`
`text-6xl`

`text-size`

---

class="font-bold"

---

class="uppercase"

---


```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main>
        <div>
            <a href="#">Log in</a>
            <a href="#">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold">Latest Recipes</h4>

            <div>
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold">Most Popular</h4>

            <div>
                <!-- cards go here -->
            </div>

            <div>
                <div>Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #4 - Margin, Padding & Borders](https://www.youtube.com/watch?v=1g4W2U-l350&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=4)


`p-64`

`padding-rem`

`py`
`paddingYdirection`

`px`
`paddingXdirection`

`pt`
`paddingTop`

`pr`
`paddingRight`

`pb`
`paddingBottom`

`pl`
`paddingLeft`

`m-12`

`margin-rem`

`border-1`

`borderwidth-px`

`border-t-1`

`borderwidth-px`

`borderwidth-top-px`

`border-r-1`

`borderwidth-right-px`

`borderwidth-px`

`border-b-1`

`borderwidth-bottom-px`

`border-l-1`

`borderwidth-left-px`

`border-gray-200`

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6">
        <div>
            <a href="#">Log in</a>
            <a href="#">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8">
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div>
                <div>Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #5 - Tailwind Config](https://www.youtube.com/watch?v=6UVQlB1eo5A&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=5)

terminal:

`npx tailwindcss init --full`

`tailwind.config.js`

object. with values...

```
```

`npm run build-css` - will apply any changes made to the object.

`npx tailwindcss init`

```
module.exports = {
    purge: [],
    theme: {
        extend: {
            colors: {
                primary: '#FF6363'
                secondary: {
                    100: '#E2E2D5',
                    200: '#888883',
                }
            }
        },
    },
    variants: {},
    plugins: [],
}
```

`npm run build-css` - will apply any changes made to the object.

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6">
        <div>
            <a href="#" class="text-primary">Log in</a>
            <a href="#" class="text-primary">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8">
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div>
                <div class="bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

VS Code Plugin: Tailwind CSS IntelliSense

## [Tailwind CSS Tutorial #6 - Custom Fonts](https://www.youtube.com/watch?v=arfDRUIZOiw&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=6)

`class="font-sans"` default...
`class="font-serif"`
`class="font-mono"`


styles.css `@import` the font..



```
module.exports = {
    purge: [],
    theme: {
        extend: {
            colors: {
                primary: '#FF6363'
                secondary: {
                    100: '#E2E2D5',
                    200: '#888883',
                }
            },
            fontFamily: {
                body: ['Nunito']
            }

        },
    },
    variants: {},
    plugins: [],
}
```

`npm run build-css`

`class="font-body"`

## [Tailwind CSS Tutorial #7 - Using Flexbox](https://www.youtube.com/watch?v=WK6u8YDYqak&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=7)

Learn Flexbox before doing this...

`class="flex justify-?"`

`class="flex justify-end"`


```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6">
        <div class="flex justify-end">
            <a href="#" class="text-primary">Log in</a>
            <a href="#" class="text-primary ml-2">Sign up</a>
        </div>


        <!--
        
        <div class="flex item-end justify-center">
            <div class="bg-red-500 h-4 w-6"></div>
            <div class="bg-blue-500 h-8 w-6"></div>
            <div class="bg-green-500 h-12 w-6"></div>
        </div> 
        
        -->



        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8">
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #8 - Responsive Classes](https://www.youtube.com/watch?v=VYFjvMfVv2o&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=8)

`sm`, `md`, `lg`, `xl` device width and up.. mobile first...

`sm:bg-green-500`

`text-green-500 sm:text-red-500 lg:text-blue-500`

`text-sm md:text-xl`



```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="text-primary">Log in</a>
            <a href="#" class="text-primary ml-2">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8">
                <!-- cards go here -->
                <div>
                    <img src="img/stew.jpg" alt="">
                    <div>
                        <span>5 Bean Chilli Stew</span>
                        <span>Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #9 - Cards](https://www.youtube.com/watch?v=vqKie-xmcFs&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=9)

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600"> <!-- content wrapper -->
    <div> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="text-primary">Log in</a>
            <a href="#" class="text-primary ml-2">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8">
                <!-- cards go here -->
                <div class="bg-white rounded overflow-hidden shadow-md">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #10 - Badges](https://www.youtube.com/watch?v=cY0XJY98d3w&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=10)

```
<!-- cards go here -->
<div class="bg-white rounded overflow-hidden shadow-md relative">
    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
    <div class="m-4">
        <span class="bold">5 Bean Chilli Stew</span>
        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
    </div>
    <div class="bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2">
        <span>25 mins</span>
    </div>
</div>
```

## [Tailwind CSS Tutorial #11 - @apply Directive](https://www.youtube.com/watch?v=somWrB-wumY&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=11)

Alot of classes...

styles.css

```

.card {
    @apply bg-white rounded overflow-hidden shadow-md relative;
}

.badge {
    @apply bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2;
}

```

```
<!-- cards go here -->
<div class="card">
    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
    <div class="m-4">
        <span class="bold">5 Bean Chilli Stew</span>
        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
    </div>
    <div class="badge">
        <span>25 mins</span>
    </div>
</div>
<div class="card">
    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
    <div class="m-4">
        <span class="bold">Veg Noodles</span>
        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
    </div>
    <div class="badge">
        <span>25 mins</span>
    </div>
</div>
<div class="card">
    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
    <div class="m-4">
        <span class="bold">Tofu Curry</span>
        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
    </div>
    <div class="badge">
        <span>25 mins</span>
    </div>
</div>
```
`npm run build-css`

## [Tailwind CSS Tutorial #12 - Grids](https://www.youtube.com/watch?v=_r2qB44o_Fs&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=12)

Need a basic understanding of CSS Grid first...

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1"> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="text-primary">Log in</a>
            <a href="#" class="text-primary ml-2">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #13 - Buttons](https://www.youtube.com/watch?v=kMiMlB5PZRM&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=13)

```
.btn {
    @apply rounded-full py-2 px-3 uppercase text-xs font-bold cursor-pointer tracking-wider;
}
```

`npm run build-css`

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1"> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #14 - Icons](https://www.youtube.com/watch?v=aNmBiqK2uQ0&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=14)

https://heroicons.dev/

```
<svg class="w-48" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
  <path stroke-linecap="round" d="M16.5 12a4.5 4.5 0 11-9 0 4.5 4.5 0 019 0zm0 0c0 1.657 1.007 3 2.25 3S21 13.657 21 12a9 9 0 10-2.636 6.364M16.5 12V8.25"></path>
</svg>

<svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
</svg>

```

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1"> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"></path>
                        </svg>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"></path>
                        </svg>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"></path>
                        </svg>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #15 - Hover Effects](https://www.youtube.com/watch?v=t19h2Ki_DUw&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=15)

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1"> <!-- start nav -->
        <nav>
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/" class="hover:text-gray-700">Food Ninja</a>
                </h1>
            </div>
            <ul>
                <li class="text-gray-700 font-bold">
                    <a href="#">
                        <span>Home</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"></path>
                        </svg>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>About</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"></path>
                        </svg>
                    </a>
                </li>
                <li>
                    <a href="#">
                        <span>Contact</span>
                        <svg class="w-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"></path>
                        </svg>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2 hover:bg-primary hover:text-white">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2 hover:bg-primary hover:text-white">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200 hover:shadow-inner">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #16 - Responsive Nav (part 1)](https://www.youtube.com/watch?v=Yn7C8MI6ymo&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=16)

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1 md:flex md:justify-end"> <!-- start nav -->
        <nav class="text-right">
            <div>
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/" class="hover:text-gray-700">Food Ninja</a>
                </h1>
            </div>
            <ul class="text-sm mt-6">
                <li class="text-gray-700 font-bold py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-primary">
                        <span>Home</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>About</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>Contact</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"></path>
                        </svg>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2 hover:bg-primary hover:text-white">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2 hover:bg-primary hover:text-white">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200 hover:shadow-inner">Load more</div>
            </div>
        </div>
    </main>
</div>
```

## [Tailwind CSS Tutorial #17 - Responsive Nav (part 2)](https://www.youtube.com/watch?v=kdF-OVtBtHU&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=17)

index.js 

```
const burger = document.querySelector('#burger');
const menu = document.querySelector('#menu');
burger.addEventListener('click', () => {
    if (menu.classList.contains('hidden')) {
        men.classList.remove('hidden');
    } else {
        men.classList.add('hidden');
    }
})
```

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1 md:flex md:justify-end"> <!-- start nav -->
        <nav class="text-right">
            <div class="flex justify-between items-center">
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/" class="hover:text-gray-700">Food Ninja</a>
                </h1>
                <div class="px-4 cursor-pointer md:hidden" id="burger">
                    <svg class="w-6" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"></path>
                    </svg>
                </div>
            </div>
            <ul class="text-sm mt-6 hidden md:block" id="menu">
                <li class="text-gray-700 font-bold py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-primary">
                        <span>Home</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>About</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>Contact</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"></path>
                        </svg>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2 hover:bg-primary hover:text-white">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2 hover:bg-primary hover:text-white">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200 hover:shadow-inner">Load more</div>
            </div>
        </div>
    </main>
</div>

<script src="index.js"></script>
```

## [Tailwind CSS Tutorial #18 - Transitions](https://www.youtube.com/watch?v=0zA6GZa2ZKc&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=18)

```
<link rel="stylesheet" href="styles.css">

<div class="text-gray-600 grid md:grid-cols-3"> <!-- content wrapper -->
    <div class="md:col-span-1 md:flex md:justify-end"> <!-- start nav -->
        <nav class="text-right">
            <div class="flex justify-between items-center">
                <h1 class="font-bold uppercase p-4 border-b border-gray-100">
                    <a href="/" class="hover:text-gray-700">Food Ninja</a>
                </h1>
                <div class="px-4 cursor-pointer md:hidden" id="burger">
                    <svg class="w-6" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"></path>
                    </svg>
                </div>
            </div>
            <ul class="text-sm mt-6 hidden md:block" id="menu">
                <li class="text-gray-700 font-bold py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-primary">
                        <span>Home</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>About</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M9.879 7.519c1.171-1.025 3.071-1.025 4.242 0 1.172 1.025 1.172 2.687 0 3.712-.203.179-.43.326-.67.442-.745.361-1.45.999-1.45 1.827v.75M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9 5.25h.008v.008H12v-.008z"></path>
                        </svg>
                    </a>
                </li>
                <li class="py-1">
                    <a href="#" class="px-4 flex justify-end border-r-4 border-white">
                        <span>Contact</span>
                        <svg class="w-5 ml-2" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"></path>
                        </svg>
                    </a>
                </li>
            </ul>
        </nav>
    </div> <!-- end nav -->
    <main class="px-16 py-6 br-gray-100 md:col-span-2">
        <div class="flex justify-center md:justify-end">
            <a href="#" class="btn text-primary border-primary md:border-2 hover:bg-primary hover:text-white transition ease-out duraction-500">Log in</a>
            <a href="#" class="btn text-primary ml-2 border-primary md:border-2 hover:bg-primary hover:text-white transition ease-out duraction-500">Sign up</a>
        </div>
        <header>
            <h2 class="text-gray-700 text-6xl font-semibold">Recipes</h2>
            <h3 class="text-2xl font-semibold">For Ninjas</h3>
        </header>
        <div>
            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Latest Recipes</h4>

            <div class="mt-8 grid lg:grid-cols-3 gap-10">
                <!-- cards go here -->
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">5 Bean Chilli Stew</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Veg Noodles</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
                <div class="card hover:shadow-lg">
                    <img src="img/stew.jpg" alt="" class="w-full h-32 sm:h-48 object-cover">
                    <div class="m-4">
                        <span class="bold">Tofu Curry</span>
                        <span class="block text-gray-500 text-sm">Recipe by Mario</span>
                    </div>
                    <div class="badge">
                        <svg class="w-5 inline-block" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"></path>
                        </svg>
                        <span>25 mins</span>
                    </div>
                </div>
            </div>

            <h4 class="font-bold mt-12 pb-2 border-b border-gray-200">Most Popular</h4>

            <div class="mt-8">
                <!-- cards go here -->
            </div>

            <div class="flex justify-center">
                <div class="btn bg-secondary-100 text-secondary-200 hover:shadow-inner transform hover:scale-125 hover:bg-opacity-50 transition ease-out duraction-300">Load more</div>
            </div>
        </div>
    </main>
</div>

<script src="index.js"></script>
```

## [Tailwind CSS Tutorial #19 - Wrap Up](https://www.youtube.com/watch?v=LqSOFdSupks&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw&index=19)

Check the document to learn more...
