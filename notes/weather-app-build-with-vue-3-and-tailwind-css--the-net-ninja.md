[Weather App Build (with Vue 3 & Tailwind CSS) - The Net Ninja](https://www.youtube.com/playlist?list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ)

[Weather App Build (Vue 3 & Tailwind) #1 - Introduction - The Net Ninja](https://www.youtube.com/watch?v=gUsBaB5ViAo&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=1)

with/by John Komarnicki

- Vue 3
- TailwindCSS
- OpenWeather (API)

Search bar to search city.
LocalStorage to Save Cities.

Course files: https://github.com/johnkomarnicki/net_ninja_vue_3_weather_app

VS Code Extensions used:

- Vue Language Features (Volar)
- Vue VSCode Snippets

- Tailwind CSS IntelliSense

`npm init vue@latest`
`y`
`vue-project`
`No`
`No`
`Yes` Add Vue Router for Single Page Application development?
`No`
`No`
`No`

`cd vue-project`
`npm install`
`npm run dev`

`src/assets/` remove all files.
`src/components/` remove all files.
`src/router/index.js` remove `about`.
`src/views/AboutView.vue` remove file.
`src/views/HomeView.vue` remove the `TheWelcome`.
`src/App.js` remove and replace with a clean v3 boilderplate template (vbase-3-setup)

```
<template>
    <div>
        <RouterView />
    </div>
</template>
<script setup>
import { RouterView } from "vue-router"
</script>
<style lang="scss" scoped></style>

```

[Weather App Build (Vue 3 & Tailwind) #2 - Tailwind Setup - The Net Ninja](https://www.youtube.com/watch?v=TsQVdEekvtE&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=3)

`npm install -D tailwindcss postcss autoprefixer`
`npx tailwindcss init -p`

`tailwind.config.js`

```
module.exports = {
    content: [
        "./index.html",
        "./src/**/*.{vue,js,ts,jsx,tsx}"
    ],
    theme: {
        extend: {
            colors: {
                "weather-primary": "#00668A",
                "weather-secondary": "#004E71",
            },
        },
        fontFamily: {
            Roboto: ["Roboto, Sans-serif"],
        },
        container: {
            padding: "2rem",
            center: true,
        },
        screens: {
            sm: "640px", 
            md: "768px",
        }`
    },
    plugins: [],
};
```

`src/assets/tailwind.css`

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

`src/main.js`

```
import "./assets/tailwind.css";

```

`src/index.html`

```
<!DOCTYPE html>
<html lang="en">
    <head>
        ...
        <link href="" rel="stylesheet"> <!-- Link to custom font... -->
    <head>
    <body>
        ...
    </body>
</html>
```

[Weather App Build (Vue 3 & Tailwind) #3 - Navigation - The Net Ninja](https://www.youtube.com/watch?v=AoIn_xiol78&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=4)

https://cdnjs.com/, font-awesome

`src/index.html`

```
<!DOCTYPE html>
<html lang="en">
    <head>
        ...
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" integrity="sha512-iecdLmaskl7CVkqkXNQ/ZH/XLlvWZOJyj7Yy7tcenmpD1ypASozpmT/E0iPtmFIB46ZmdtAc9eNBvH0H/ZpiBw==" crossorigin="anonymous" referrerpolicy="no-referrer" /> <!-- Link to font-awesome... -->
    <head>
    <body>
        ...
    </body>
</html>
```

`src/components/SiteNavigation.vue`

`vbase-3-setup`

```
<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6"></nav>
        <RouterLink :to="{name: 'home'}">
            <div class="flex items-center gap-3">
                <i class="fa-solid fa-sun text-2xl"></i>
                <p classs="text-2xl">The Local Weather</p>
            </div>
        </RouterLink>
        <div class="flex gap-3 flex-1 justify-end">
            <i class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer"></i>
            <i class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"></i>
        </div>
    </header>
</template>

<script setup>
import { RouterLink } from "vue-router";
</script>

<style lang="scss" scoped></style>
```

`src/App.vue`

```
<template>
    <div class="flex flex-col min-h-screen font-Roboto bg-weather-primary">
        <SiteNavigation />
        <RouterView />
    </div>
</template>

<script setup>
import { RouterView } from "vue-router";
import SiteNaigation from "./components/SiteNavigation.vue"
</script>

<style lang="scss" scoped></style>
```

[Weather App Build (Vue 3 & Tailwind) #4 - Reusable Modal - The Net Ninja](https://www.youtube.com/watch?v=NilffTjcDVA&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=5)

`src/components/BaseModal.vue`

`vbase-3-setup`

```
<template>
    <Teleport to="body">
        <Transition name="modal-outer">
            <div v-show="modalActive" class="absolute w-ful bg-back bg-opacity-30 h-screen top-0 left-0 flex justify-center px-8">
                <Transition name="modal-inner">
                    <div v-if="modalActive" class="p-4 bg-white self-start mt-32 max-w-screen-md">
                        <slot />
                        <button class="text-white mt-8 bg-weather-primary py-2 px-6" @click="$emit('close-modal')">Close</button>
                    </div>
                </Trransition>
            </div>
        </Transition>
    </Teleport>
</template>

<script setup>
defineEmits(["close-modal"]);
defineProp({
    modalActive: {
        type: Boolean,
        default: false,
    },
});
</script>

<style lang="scss" scoped>
    .modal-outer-enter-active,
    .modal-outer-leave-active {
        transition: opacity 0.3s cubic-bezier(0.52, 0.02, 0.19, 1.02);
    }
    .modal-outer-enter-form,
    .modal-outer-leave-to {
        opacity: 0;
    }
    .modal-innter-enter-active {
        transition: opacity 0.3s cubic-bezier(0.52, 0.02, 0.19, 1.02)  0.15s;
    }
    .modal-inner-leave-active {
        transition: opacity 0.3s cubic-bezier(0.52, 0.02, 0.19, 1.02);
    }
    .modal-inner-enter-from {
        opacity: 0;
        transform: scale(0.8);
    }
    .modal-inner-leace-to {
        transform: scale(0.8);
    }
</style>
```

`src/components/SiteNavigation.vue`

```
<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
            <RouterLink :to="{name: 'home'}">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-sun text-2xl"></i>
                    <p classs="text-2xl">The Local Weather</p>
                </div>
            </RouterLink>
            <div class="flex gap-3 flex-1 justify-end">
                <i class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer" @click="toggleModal"></i>
                <i class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"></i>
            </div>
            <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
                <h1 class="text-black">Hello From Modal</h1> <!-- see repo for full content -->
            </BaseModal>
        </nav>
    </header>
</template>

<script setup>
import { RouterLink } from "vue-router";
import { BaseModal } from "./BaseModal.vue";


const modalActive = ref(null);
const toggleModal = () => {
    modalActive.value = !modalActive.value;
}
</script>

<style lang="scss" scoped></style>
```

Check out the CSS-Based Transitions Vue.js documentation.

[Weather App Build (Vue 3 & Tailwind) #5 - City Search - The Net Ninja](https://www.youtube.com/watch?v=5pTzHoliXUQ&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=6)

`src/views/HomeView.vue`

```
<template>
    <main class="container text-white">
        <div class="pt-4 mb-8 relative">
            <input 
                type="text" 
                v-model="searchQuery"
                @input="getSearchResults"
                placeholder="Search for a city or state" 
                class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
            <ul 
                class="absolute bg-weather-secondary text-white w-full shadow-md py-2 px-1 top-[66px]"
                v-if="mapboxSearchResults"
            >
                <li v-for="searchResults in mapboxSearchResults" 
                    :key="searchResult.id"
                    class="py-2 cursor-pointer">
                    {{ searchResult.place_name }}    
                </li>
            </ul>
        </div>
    </main>
</template>
<script setup>
import { ref } from "vue";
import axios from "axios";

const mapboxAPIKey = "fhjbjsdkjdlk";
const searchQuery = ref("");
const queryTimeout = ref(null);
const mapboxSearchResults = ref(null);

const getSearchResults = () => {
    clearTimeout (queryTimeout.value);
    queryTimeout.value = setTimeout(async () => {
        if(searchQuery.value !== "") {
            const result = await axios.get(`endpoint_url/mapbox.places/${searchQuery}.json?access_token=${mapboxAPIKey}&types=place`);
            mapboxSearchResults.value = result.data.features;
            console.log(mapboxSearchResults.value);
            return;
        }
        mapboxSearchResults.value = null;
    }, 300);
}

</script>
```

https://www.mapbox.com/
Create Account... Have to give them your card details...
Documentation > Search > Search API > Geocoding API

[Weather App Build (Vue 3 & Tailwind) #6 - Handling API Errors - The Net Ninja](https://www.youtube.com/watch?v=KvPYw-OyMZA&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=7)

`src/views/HomeView.vue`

```
<template>
    <main class="container text-white">
        <div class="pt-4 mb-8 relative">
            <input 
                type="text" 
                v-model="searchQuery"
                @input="getSearchResults"
                placeholder="Search for a city or state" 
                class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
            <ul 
                class="absolute bg-weather-secondary text-white w-full shadow-md py-2 px-1 top-[66px]"
                v-if="mapboxSearchResults"
            >
                <p v-if="searchError">
                    Sorry, something went wrong, please try again.
                </p>
                <p v-if="!serverError && mapboaxSearchResults.length === 0">
                    No results match your query, try a different term.
                </p>
                <template v-else> <!-- ? I have had issues with this before ? -->
                    <li v-for="searchResults in mapboxSearchResults" 
                        :key="searchResult.id"
                        class="py-2 cursor-pointer">
                        {{ searchResult.place_name }}    
                    </li>
                </template>
            </ul>
        </div>
    </main>
</template>
<script setup>
import { ref } from "vue";
import axios from "axios";

const mapboxAPIKey = "fhjbjsdkjdlk";
const searchQuery = ref("");
const queryTimeout = ref(null);
const mapboxSearchResults = ref(null);
const searchError = ref(null);

const getSearchResults = () => {
    clearTimeout (queryTimeout.value);
    queryTimeout.value = setTimeout(async () => {
        if(searchQuery.value !== "") {
            try {
                const result = await axios.get(`endpoint_url/mapbox.places/${searchQuery}.json?access_token=${mapboxAPIKey}&types=place`);
                mapboxSearchResults.value = result.data.features;
            } catch {
                searchResult.value = true;
            }

            return;
        }
        mapboxSearchResults.value = null;
    }, 300);
}

</script>
```

[Weather App Build (Vue 3 & Tailwind) #7 - Redirect Route - The Net Ninja](https://www.youtube.com/watch?v=7l6he407PhY&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=8)


`src/views/CityView.vue`

`v-base3`

```
<template>
    <div></div>
</template>

<script setup></script>
```

`src/router/index.js`

```
...
import HomeView from "../views/HomeView.vue"
import HomeView from "../views/CityView.vue"

const router = createRouter({
    ...
    routes: [
        {
            path: "/",
            name: "home",
            component: HomeView
        },
        {
            path: "/weather/:state/:city",
            name: "cityView",
            component: CityView,
        },
    ]
})
...
```

`src/views/HomeView.vue`

```
<template>
    <main class="container text-white">
        <div class="pt-4 mb-8 relative">
            <input 
                type="text" 
                v-model="searchQuery"
                @input="getSearchResults"
                placeholder="Search for a city or state" 
                class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
            <ul 
                class="absolute bg-weather-secondary text-white w-full shadow-md py-2 px-1 top-[66px]"
                v-if="mapboxSearchResults"
            >
                <p v-if="searchError">
                    Sorry, something went wrong, please try again.
                </p>
                <p v-if="!serverError && mapboaxSearchResults.length === 0">
                    No results match your query, try a different term.
                </p>
                <template v-else> <!-- ? I have had issues with this before ? -->
                    <li v-for="searchResults in mapboxSearchResults" 
                        :key="searchResult.id"
                        class="py-2 cursor-pointer"
                        @click="previewCity(searchResult)">
                        {{ searchResult.place_name }}    
                    </li>
                </template>
            </ul>
        </div>
    </main>
</template>
<script setup>
import { ref } from "vue";
import axios from "axios";
import { useRouter } for "vue-router";

const router = useRouter();

const previewCity = (searchResult) => {
    // console.log(searchResult);
    const [city, state] = searchResult.place_name.split(",");
    // console.log(city, state);
    router.push({
        name: "cityView",
        params: { state: state.replaceAll(" ", ""), city: city.replaceAll(" ", "")},
        query: {
            lat: searchResult.geometry.coordinates[1],
            lng: searchResult.geometry.coordinates[0],
            preview: true,
        }
    })
};

const mapboxAPIKey = "fhjbjsdkjdlk";
const searchQuery = ref("");
const queryTimeout = ref(null);
const mapboxSearchResults = ref(null);
const searchError = ref(null);

const getSearchResults = () => {
    clearTimeout (queryTimeout.value);
    queryTimeout.value = setTimeout(async () => {
        if(searchQuery.value !== "") {
            try {
                const result = await axios.get(`endpoint_url/mapbox.places/${searchQuery}.json?access_token=${mapboxAPIKey}&types=place`);
                mapboxSearchResults.value = result.data.features;
            } catch {
                searchResult.value = true;
            }

            return;
        }
        mapboxSearchResults.value = null;
    }, 300);
}

</script>
```

[Weather App Build (Vue 3 & Tailwind) #8 - Handling Async Data - The Net Ninja](https://www.youtube.com/watch?v=M66Vo8P7WSw&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=9)

`src/views/CityView.vue`

```
<template>
    <div>
        <Suspense>
            <AsyncCityView />
            <tample #fallback>
                <p>Loading...</p>
            </template>
        </Suspense>
    </div>
</template>

<script setup>
import AsyncCityView from "../components/AsyncCityView.vue";
</script>
```

`src/components/AsyncCityView.vue`

`v-base3`

```
<template>
    <div></div>
</template>

<script setup>
import axios from 'axios';
import { useRoute } from 'vue-router';

const route = useRoute();
const getWeatherData = async () => {
    try {
        const weatherData = await axios.get(`endpoint_url/onecall?lat=${route.query.lat}&lon=${route.query.lng}&exclude=${}&appid=hjkhjrdfkjhjkhjk&units=imperial`)
        
        // calc current date & time
        ...
        // calc hourly weather offset
        ...

        return weatherData;



    
    } catch (err) {
        console.log(err);
    }
}
const weatherData = await getWeatherData();
console.log(weatherData);
</script>
```

https://openweathermap.org/
Create Account...
My API Keys > Create/Name/Generate
One Call API 1.0

[Weather App Build (Vue 3 & Tailwind) #9 - City View Layout - The Net Ninja](https://www.youtube.com/watch?v=_p-gU3alR0M&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=10)


`src/components/AsyncCityView.vue`

```
<template>
    <div class="flex flex-col flex-1 items-center">
        <!-- Banner -->
        <div v-if="route.query.preview" class="text-white p-4 bg-weather-secondary w-full text-center">
            <p>
                You are currently previewing this city, click the  "+" icon to start tracking this city.
            </p>
        </div>
        <!-- Weather Overview -->
        <div class="flex flex-col items-center text-white py-12">
            <h1 class="text-4xl mb-2">{{ route.params.city }}</h1>
            <p class="text-sm mb-12">
                {{ ... }}
                {{ ... }}
            </p>
            <p class="text-8xl mb-8">
                {{ Math.round(weatherData.current.temp) }}&deg;
            </p> 
            <p>
                Feels like
                {{ ... }}
            </p>
            <p>
                {{ ...}}
            </p>
            <img
                class="w-[150px] h-auto"
                :src="
                `http://openweathermapp.org/image/wn/${weatherData.current.weather[0].icon}@2x.png`
                "
                alt=""
            />
        </div>
        <hr class="border-white border-opacity-10 border w-full" />
        <!-- Hourly Weather -->
        <div class="max-w-screen-md w-full py-12">        
            <div class="mx-8 text-white">
                <h2 class="mb-4">Hourly Weather</h2>
                <div class="flex gap-100 overflow-x-scroll">
                    <div 
                        v-for="hourData in weatherData.hourly" 
                        :key="hourData.dt"
                        class="flex flex-col gap-4 items-center"
                    >
                        <p class="whitespace-nowrap text-md">
                            {{ ... }}
                        </p>
                        <img
                            class="w-auto h-[50px] object-cover"
                            :src="
                            `http://openweathermapp.org/image/wn/${hourData.weather[0].icon}@2x.png`
                            "
                            alt=""
                        />
                        <p class="text-xl">
                            {{ ... }}&deg;
                        </p>
                    </div>
                </div>
            </div>
        </div>
        <!-- Weekly Weather -->
        <div class="max-w-screen-md w-full py-12">
            <div class="mx-8 text-white">
                <h2 class="mb-4">7 Day Forecast</h2>
                <div 
                    v-for="day in weahterData.daily"
                    :key="day.dt"
                    class="flex items-center"
                >
                    <p class="flex-1">
                        {{ ... }}
                    </p>
                    <img
                        class="w-[50px] h-[50px] object-cover"
                        :src="
                        `http://openweathermapp.org/image/wn/${day.weather[0].icon}@2x.png`
                        "
                        alt=""
                    />
                    <div class="flex gap-2 flex-1 justify-end">
                        <p>H: {{ ... }}</p>
                        <p>L: {{ ... }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios';
import { useRoute } from 'vue-router';

const route = useRoute();
const getWeatherData = async () => {
    try {
        const weatherData = await axios.get(`endpoint_url/onecall?lat=${route.query.lat}&lon=${route.query.lng}&exclude=${}&appid=hjkhjrdfkjhjkhjk&units=imperial`)
        
        // calc current date & time
        ...
        // calc hourly weather offset
        ...

        return weatherData.data;
    } catch (err) {
        console.log(err);
    }
}
const weatherData = await getWeatherData();
console.log(weatherData);
</script>
```

Recomend: Vue.js devtools for chrome.


[Weather App Build (Vue 3 & Tailwind) #10 - Adding Cities to Local Storage - The Net Ninja](https://www.youtube.com/watch?v=NLZdCzqpZvw&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=11)

`src/components/SiteNavigation.vue`

```
<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
            <RouterLink :to="{name: 'home'}">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-sun text-2xl"></i>
                    <p classs="text-2xl">The Local Weather</p>
                </div>
            </RouterLink>
            <div class="flex gap-3 flex-1 justify-end">
                <i class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer" @click="toggleModal"></i>
                <i 
                    class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"
                    @click="addCity"    
                    v-if="route.query.preview"
                ></i>
            </div>
            <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
                <h1 class="text-black">Hello From Modal</h1> <!-- see repo for full content -->
            </BaseModal>
        </nav>
    </header>
</template>

<script setup>
import { ref } from "vue";
import { uid } from 'uid'; 


import { RouterLink, useRoute, useRouter } from "vue-router";
import { BaseModal } from "./BaseModal.vue";

const savedCities = red([]);
const route = useRoute();
const router = useRouter();

const addCity = () => {
    if (localStorage.gettItem('savedCities')) {
        savedCities.value = JSON.parse(
            localStorage.getItem("savedCities")
        );
    }

    const locationObj = {
        id: uid(),
        state: route.params.state,
        city: route.params.city,
        coords: {
            lat: route.query.lat,
            lng: route.query.lng,
        }
    };
    savedCities.value.push(locationObj);
    localStorage.setItem(
        'SavedCities', 
        JSON.stringify(savedCities.value)
    );

    let query = Object.assign({}, route.query);
    delete query.preview;
    router.rplace({ query });
};

const modalActive = ref(null);
const toggleModal = () => {
    modalActive.value = !modalActive.value;
}
</script>

<style lang="scss" scoped></style>
```

`npm i uid`

[Weather App Build (Vue 3 & Tailwind) #11 - Retrieve Data from Local Storage - The Net Ninja](https://www.youtube.com/watch?v=Dr0r9TitMS8&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=12)

`src/components/CityList.vue`

`v-base3-setup`


```
<template>
    <div v-for="city in savedCities" :key="city.id">
        <CityCard :city="city" @click="goToCityView(city)" />
    </div>
    <p v-if="savedCities.length === 0">
        No locations added. To start tracking a location, search in the field above.
    </p>
</template>

<script setup>
import axios from "axios"
import { ref } from "vue";

const savedCities = ref([]);
const getCities = () => {
    if (localStorage.getItem('savedCities')) {
        savedCities.value = JSON.parse(
            localStorage.getItem("savedCities")
        );
        const requests = [];
        savedCities.value.forEach((city) => {
            requests.push(
                axios.get('endpoint_url/weather?lat${city.coords.lat}&lon=${city.coords.lng}&appid=jhkjhdshlkjfs&units=imperial')
            );
        });

        const weatherData = await Promise.all(requests);
        weatherData.forEach((value, index) => {
            savedCities.value[index].weather = value.data;
        })
    }
}
await getCities();

const router = useRouter();
const goToCityView = (city) => {
    router.push({
        name: "cityView",
        params: { state: city.state, city: city.city },
        query: { lat: city.coords.lat, lng: city.coords.lng },
    });
};

</script>
```

using current weather...

`src/views/HomeView.vue`

```
<template>
    <main class="container text-white">
        <div class="pt-4 mb-8 relative">
            <input 
                type="text" 
                v-model="searchQuery"
                @input="getSearchResults"
                placeholder="Search for a city or state" 
                class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
            <ul 
                class="absolute bg-weather-secondary text-white w-full shadow-md py-2 px-1 top-[66px]"
                v-if="mapboxSearchResults"
            >
                <p v-if="searchError">
                    Sorry, something went wrong, please try again.
                </p>
                <p v-if="!serverError && mapboaxSearchResults.length === 0">
                    No results match your query, try a different term.
                </p>
                <template v-else> <!-- ? I have had issues with this before ? -->
                    <li v-for="searchResults in mapboxSearchResults" 
                        :key="searchResult.id"
                        class="py-2 cursor-pointer"
                        @click="previewCity(searchResult)">
                        {{ searchResult.place_name }}    
                    </li>
                </template>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <Suspense>
                <CityList />
                <template #fallback>
                    <p>Loading...</p>
                </template>
            </Suspense>
        </div>
    </main>
</template>
<script setup>
import { ref } from "vue";
import axios from "axios";
import { useRouter } for "vue-router";

const router = useRouter();

const previewCity = (searchResult) => {
    // console.log(searchResult);
    const [city, state] = searchResult.place_name.split(",");
    // console.log(city, state);
    router.push({
        name: "cityView",
        params: { state: state.replaceAll(" ", ""), city: city.replaceAll(" ", "")},
        query: {
            lat: searchResult.geometry.coordinates[1],
            lng: searchResult.geometry.coordinates[0],
            preview: true,
        }
    })
};

const mapboxAPIKey = "fhjbjsdkjdlk";
const searchQuery = ref("");
const queryTimeout = ref(null);
const mapboxSearchResults = ref(null);
const searchError = ref(null);

const getSearchResults = () => {
    clearTimeout (queryTimeout.value);
    queryTimeout.value = setTimeout(async () => {
        if(searchQuery.value !== "") {
            try {
                const result = await axios.get(`endpoint_url/mapbox.places/${searchQuery}.json?access_token=${mapboxAPIKey}&types=place`);
                mapboxSearchResults.value = result.data.features;
            } catch {
                searchResult.value = true;
            }

            return;
        }
        mapboxSearchResults.value = null;
    }, 300);
}

</script>
```

`src/components/CityCard.vue`

`v-base3-setup`


```
<template>
    <div class="flex py-6 px-3 bg-weather-secondary rounded-md shadow-md">
        <div class="flex flex-col flex-1">
            <h2 class="text-3xl">{{ city.city }}</h2>
            <h3>{{ city.state }}</h3>
        </div>
        <div class="flex flex-col gap-2">
            <p class="text-3xl self-end">
                {{ ... }}&deg;
            </p>
            <div class="flex gap-2">
                <span class="text-xs">
                    H:
                    {{ ... }}&deg;
                </span>
                <span class="text-xs">
                    L:
                    {{ ... }}&deg;
                </span>
            </div>
        </div>
    </div>
</template>

<script setup>
defineProps({
    city: {
        type: Object,
        default: () => {

        },
    },
})
</script>
```

[Weather App Build (Vue 3 & Tailwind) #12 - Removing Cities - The Net Ninja](https://www.youtube.com/watch?v=l31_fyp-AwQ&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=13)


`src/components/AsyncCityView.vue`

```
<template>
    <div class="flex flex-col flex-1 items-center">
        <!-- Banner -->
        <div v-if="route.query.preview" class="text-white p-4 bg-weather-secondary w-full text-center">
            <p>
                You are currently previewing this city, click the  "+" icon to start tracking this city.
            </p>
        </div>
        <!-- Weather Overview -->
        <div class="flex flex-col items-center text-white py-12">
            <h1 class="text-4xl mb-2">{{ route.params.city }}</h1>
            <p class="text-sm mb-12">
                {{ ... }}
                {{ ... }}
            </p>
            <p class="text-8xl mb-8">
                {{ Math.round(weatherData.current.temp) }}&deg;
            </p> 
            <p>
                Feels like
                {{ ... }}
            </p>
            <p>
                {{ ...}}
            </p>
            <img
                class="w-[150px] h-auto"
                :src="
                `http://openweathermapp.org/image/wn/${weatherData.current.weather[0].icon}@2x.png`
                "
                alt=""
            />
        </div>
        <hr class="border-white border-opacity-10 border w-full" />
        <!-- Hourly Weather -->
        <div class="max-w-screen-md w-full py-12">        
            <div class="mx-8 text-white">
                <h2 class="mb-4">Hourly Weather</h2>
                <div class="flex gap-100 overflow-x-scroll">
                    <div 
                        v-for="hourData in weatherData.hourly" 
                        :key="hourData.dt"
                        class="flex flex-col gap-4 items-center"
                    >
                        <p class="whitespace-nowrap text-md">
                            {{ ... }}
                        </p>
                        <img
                            class="w-auto h-[50px] object-cover"
                            :src="
                            `http://openweathermapp.org/image/wn/${hourData.weather[0].icon}@2x.png`
                            "
                            alt=""
                        />
                        <p class="text-xl">
                            {{ ... }}&deg;
                        </p>
                    </div>
                </div>
            </div>
        </div>
        <!-- Weekly Weather -->
        <div class="max-w-screen-md w-full py-12">
            <div class="mx-8 text-white">
                <h2 class="mb-4">7 Day Forecast</h2>
                <div 
                    v-for="day in weahterData.daily"
                    :key="day.dt"
                    class="flex items-center"
                >
                    <p class="flex-1">
                        {{ ... }}
                    </p>
                    <img
                        class="w-[50px] h-[50px] object-cover"
                        :src="
                        `http://openweathermapp.org/image/wn/${day.weather[0].icon}@2x.png`
                        "
                        alt=""
                    />
                    <div class="flex gap-2 flex-1 justify-end">
                        <p>H: {{ ... }}</p>
                        <p>L: {{ ... }}</p>
                    </div>
                </div>
            </div>
        </div>
        <!--  -->
        <div class="flex items-center gap-2 py-12 text-white cursor-pointer duraction-150 hover:text-red-500" @click="removeCity">
            <i class="fa-solid fa-trash"></i>
            <p>Remove Citty</p>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios';
import { useRoute } from 'vue-router';

const route = useRoute();
const getWeatherData = async () => {
    try {
        const weatherData = await axios.get(`endpoint_url/onecall?lat=${route.query.lat}&lon=${route.query.lng}&exclude=${}&appid=hjkhjrdfkjhjkhjk&units=imperial`)
        
        // calc current date & time
        ...
        // calc hourly weather offset
        ...

        return weatherData.data;
    } catch (err) {
        console.log(err);
    }
}
const weatherData = await getWeatherData();
console.log(weatherData);

const router = useRouter();
const removeCity = () => {
    const cities = JSON.parse(localStorage.getItem("savedCities"));
    const updatedCities = cities.filter((city) => city.id !== route.query.id);
    localStorage.setItem('savedCities', JSON.stringify(updatedCities));
    router.push({
        name: "home",
    });
};

</script>
```

`src/components/CityList.vue`

```
<template>
    <div v-for="city in savedCities" :key="city.id">
        <CityCard :city="city" @click="goToCityView(city)" />
    </div>
    <p v-if="savedCities.length === 0">
        No locations added. To start tracking a location, search in the field above.
    </p>
</template>

<script setup>
import axios from "axios"
import { ref } from "vue";

const savedCities = ref([]);
const getCities = () => {
    if (localStorage.getItem('savedCities')) {
        savedCities.value = JSON.parse(
            localStorage.getItem("savedCities")
        );
        const requests = [];
        savedCities.value.forEach((city) => {
            requests.push(
                axios.get('endpoint_url/weather?lat${city.coords.lat}&lon=${city.coords.lng}&appid=jhkjhdshlkjfs&units=imperial')
            );
        });

        const weatherData = await Promise.all(requests);
        weatherData.forEach((value, index) => {
            savedCities.value[index].weather = value.data;
        })
    }
}
await getCities();

const router = useRouter();
const goToCityView = (city) => {
    router.push({
        name: "cityView",
        params: { state: city.state, city: city.city },
        query: { id: city.id, lat: city.coords.lat, lng: city.coords.lng },
    });
};

</script>
```

`src/components/SiteNavigation.vue`

```
<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
            <RouterLink :to="{name: 'home'}">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-sun text-2xl"></i>
                    <p classs="text-2xl">The Local Weather</p>
                </div>
            </RouterLink>
            <div class="flex gap-3 flex-1 justify-end">
                <i class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer" @click="toggleModal"></i>
                <i 
                    class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"
                    @click="addCity"    
                    v-if="route.query.preview"
                ></i>
            </div>
            <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
                <h1 class="text-black">Hello From Modal</h1> <!-- see repo for full content -->
            </BaseModal>
        </nav>
    </header>
</template>

<script setup>
import { ref } from "vue";
import { uid } from 'uid'; 


import { RouterLink, useRoute, useRouter } from "vue-router";
import { BaseModal } from "./BaseModal.vue";

const savedCities = red([]);
const route = useRoute();
const router = useRouter();

const addCity = () => {
    if (localStorage.gettItem('savedCities')) {
        savedCities.value = JSON.parse(
            localStorage.getItem("savedCities")
        );
    }

    const locationObj = {
        id: uid(),
        state: route.params.state,
        city: route.params.city,
        coords: {
            lat: route.query.lat,
            lng: route.query.lng,
        }
    };
    savedCities.value.push(locationObj);
    localStorage.setItem(
        'SavedCities', 
        JSON.stringify(savedCities.value)
    );

    let query = Object.assign({}, route.query);
    delete query.preview;
    query.id = locationObj.id;
    router.rplace({ query });
};

const modalActive = ref(null);
const toggleModal = () => {
    modalActive.value = !modalActive.value;
}
</script>

<style lang="scss" scoped></style>
```

[Weather App Build (Vue 3 & Tailwind) #13 - Animated Skeleton Placeholders - The Net Ninja](https://www.youtube.com/watch?v=8qqCLeArGgc&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=14)

`src/components/AnimatedPlaceholder.vue`

```
<template>
    <div class="bg-gradient-to-r from-gray-100 animate-pulse">
        &nbsp;
    </div>
</template>
```

`src/components/CityCardSkeleton.vue`

`vbase3-setup`

```
<template>
    <div class="flex py-6 px-3 bg-weather-secondary rounded-md shadow-md">
        <div class="flex flex-col flex-1 gap-2">
            <AnimatedPlaceholder class="max-w-[50%]"/>
            <AnimatedPlaceholder class="max-w-[40%]"/>
            <div class="flex flex-col items-end flex-1 gap-2">
                <AnimatedPlaceholder class="max-w-[50px] w-full"/>
                <AnimatedPlaceholder class="max-w-[70px] w-full"/>
            </div>
        </div>
    </div>
</template>

<script setup>
import AnimatedPlaceholder from './AnimatedPlaceholder.vue';
</script>

```

`src/views/HomeView.vue`

```
<template>
    <main class="container text-white">
        <div class="pt-4 mb-8 relative">
            <input 
                type="text" 
                v-model="searchQuery"
                @input="getSearchResults"
                placeholder="Search for a city or state" 
                class="py-2 px-1 w-full bg-transparent border-b focus:border-weather-secondary focus:outline-none focus:shadow-[0px_1px_0_0_#004E71]">
            <ul 
                class="absolute bg-weather-secondary text-white w-full shadow-md py-2 px-1 top-[66px]"
                v-if="mapboxSearchResults"
            >
                <p v-if="searchError">
                    Sorry, something went wrong, please try again.
                </p>
                <p v-if="!serverError && mapboaxSearchResults.length === 0">
                    No results match your query, try a different term.
                </p>
                <template v-else> <!-- ? I have had issues with this before ? -->
                    <li v-for="searchResults in mapboxSearchResults" 
                        :key="searchResult.id"
                        class="py-2 cursor-pointer"
                        @click="previewCity(searchResult)">
                        {{ searchResult.place_name }}    
                    </li>
                </template>
            </ul>
        </div>
        <div class="flex flex-col gap-4">
            <Suspense>
                <CityList />
                <template #fallback>
                    <!-- <p>Loading...</p> -->
                    <CityCardSkeleton />
                </template>
            </Suspense>
        </div>
    </main>
</template>
<script setup>
...
</script>
```

`src/components/CityList.vue`

```
<template>
    <div v-for="city in savedCities" :key="city.id">
        <CityCard :city="city" @click="goToCityView(city)" />
    </div>
    <p v-if="savedCities.length === 0">
        No locations added. To start tracking a location, search in the field above.
    </p>
</template>

<script setup>
import axios from "axios"
import { ref } from "vue";

const savedCities = ref([]);
const getCities = () => {
    if (localStorage.getItem('savedCities')) {
        savedCities.value = JSON.parse(
            localStorage.getItem("savedCities")
        );
        const requests = [];
        savedCities.value.forEach((city) => {
            requests.push(
                axios.get('endpoint_url/weather?lat${city.coords.lat}&lon=${city.coords.lng}&appid=jhkjhdshlkjfs&units=imperial')
            );
        });

        const weatherData = await Promise.all(requests);


        // Flicker Delay
        await new Promise((res) => setTimeout(res, 1000));


        weatherData.forEach((value, index) => {
            savedCities.value[index].weather = value.data;
        })
    }
}
await getCities();

const router = useRouter();
const goToCityView = (city) => {
    router.push({
        name: "cityView",
        params: { state: city.state, city: city.city },
        query: { id: city.id, lat: city.coords.lat, lng: city.coords.lng },
    });
};

</script>
```

`src/components/CityViewSkeleton.vue`

`vbase3-setup`

```
<template>
    ... skipped, see on GitHub.
</template>

<script setup>
import AnimatedPlaceholder from './AnimatedPlaceholder.vue';
</script>

```

`src/views/CityView.vue`

```
<template>
    <div>
        <Suspense>
            <AsyncCityView />
            <tample #fallback>
                <!-- <p>Loading...</p> -->
                <CityViewSkeleton />
            </template>
        </Suspense>
    </div>
</template>

<script setup>
import AsyncCityView from "../components/AsyncCityView.vue";
import CityViewSkeleton from "../components/CityViewSkeleton.vue";
</script>
```


`src/components/AsyncCityView.vue`

```
<template>
    ...
</template>

<script setup>
import axios from 'axios';
import { useRoute } from 'vue-router';

const route = useRoute();
const getWeatherData = async () => {
    try {
        const weatherData = await axios.get(`endpoint_url/onecall?lat=${route.query.lat}&lon=${route.query.lng}&exclude=${}&appid=hjkhjrdfkjhjkhjk&units=imperial`)
        
        // calc current date & time
        ...
        // calc hourly weather offset
        ...

        // Flicker Delay
        await new Promise((res) => setTimeout(res, 1000));

        return weatherData.data;
    } catch (err) {
        console.log(err);
    }
}
const weatherData = await getWeatherData();
console.log(weatherData);

const router = useRouter();
const removeCity = () => {
    const cities = JSON.parse(localStorage.getItem("savedCities"));
    const updatedCities = cities.filter((city) => city.id !== route.query.id);
    localStorage.setItem('savedCities', JSON.stringify(updatedCities));
    router.push({
        name: "home",
    });
};

</script>
```

[Weather App Build (Vue 3 & Tailwind) #14 - Route Transitions - The Net Ninja](https://www.youtube.com/watch?v=jsvWGacIfSc&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=15)

`src/App.vue`

```
<template>
    <div class="flex flex-col min-h-screen font-Roboto bg-weather-primary">
        <SiteNavigation />
        <RouterView v-slot="{ Component }">
            <Transition name="page" mode="out-in">
                <component :is="Component" />
            </Transition>

        </RouterView>
    </div>
</template>

<script setup>
import { RouterView } from "vue-router";
import SiteNaigation from "./components/SiteNavigation.vue"
</script>

<style>
.page-enter-active,
.page-leave-active {
    transition: 600ms ease all;
}
.page-enter-from,
.page-leave-to {
    opacity: 0;
}
</style>
```

`src/router/index.js`

```
...
import HomeView from "../views/HomeView.vue"
import HomeView from "../views/CityView.vue"

const router = createRouter({
    ...
    routes: [
        {
            path: "/",
            name: "home",
            component: HomeView,
            meta: {
                title: "Home"
            }
        },
        {
            path: "/weather/:state/:city",
            name: "cityView",
            component: CityView,
            meta: {
                title: "Weather"
            }
        },
    ]
});

router.beforeEach((to, from, next) => {
    document.title = `${
        to.params.state 
        ? `${to.params.city}, ${to.params.state}`
        : to.meta.title
    } | The Local Weather`;
    next();
})
...
```

[Weather App Build (Vue 3 & Tailwind) #15 - Deploying to Netlify - The Net Ninja](https://www.youtube.com/watch?v=i6QTDMNG0c4&list=PL4cUxeGkcC9hfoy8vFQ5tbXO3vY0xhhUZ&index=16)


Create GitHub Repo...

`git init`

`git add .`

`git commit -m "completed app"`

`git branch -M main`

`git remote add origin https://github.com/.../.../...git`

`git push -u origin main`

Add new site

Import an existing project

GitHub

Connect,

Select.
Branch,
Build command,
Publish directory,

Deploy site

Go beyond...
