<script>
import AppCard from "./AppCard.vue";

export default {
    components: {
        AppCard
    },
    name: "AppMain",
    data() {
        return {
            comicArray: [
                {
                    thumb: 'https://www.coverbrowser.com/image/action-comics/1-1.jpg',
                    price: '$19.99',
                    series: 'Action Comics',
                    type: 'comic book',
                },
                {
                    thumb: 'https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg',
                    price: '$3.99',
                    series: 'American Vampire 1976',
                    type: 'comic book',
                },
                {
                    thumb: 'https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg',
                    price: '$16.99',
                    series: 'Aquaman',
                    type: 'graphic novel',
                },
                {
                    thumb: 'https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg',
                    price: '$2.99',
                    series: 'Batgirl',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg',
                    price: '$3.99',
                    series: 'Batman',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg',
                    price: '$2.99',
                    series: 'Batman Beyond',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg',
                    price: '$3.99',
                    series: 'Batman/Superman',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg',
                    price: '$4.99',
                    series: 'Batman/Superman Annual',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg',
                    price: '$5.99',
                    series: 'Batman: The Joker War Zone',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg',
                    price: '$6.99',
                    series: 'Batman: Three Jokers',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg',
                    price: '$4.99',
                    series: 'Batman: White Knight Presents: Harley Quinn',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg',
                    price: '$16.99',
                    series: 'Catwoman',
                    type: 'graphic novel',
                },
            ],
            features: [
                {
                    img: "buy-comics-digital-comics.png",
                    name: "DIGITAL COMICS",
                    url: "#"
                },
                {
                    img: "buy-comics-merchandise.png",
                    name: "DC MERCHANDISE",
                    url: "#"
                },
                {
                    img: "buy-comics-subscriptions.png",
                    name: "SUBSCRIPTION",
                    url: "#"
                },
                {
                    img: "buy-comics-shop-locator.png",
                    name: "COMIC SHOP LOCATOR",
                    url: "#"
                },
                {
                    img: "buy-dc-power-visa.svg",
                    name: "DC POWER VISA",
                    url: "#"
                }
            ]
        }
    },
    methods: {
        getImagePath(img) {
            return new URL(`../assets/img/${img.img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <main>
        <div class="top">
            <div class="content-top">
                <button>CURRENT SERIES</button>
            </div>
            <div class="content-bottom">
                <AppCard v-for="(elem, index) in comicArray" :key="index" :thumb="elem.thumb" :series="elem.series"/>
                <button>LOAD MORE</button>
            </div>
        </div>
        <div class="bottom">
            <div class="features">
                <ul>
                    <li v-for="img in features">
                        <a :href="img.url">
                            <img :src="getImagePath(img)" alt="Logo">
                            <p>{{ img.name }}</p>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.top {
    background-color: rgba(28, 28, 28, 1);
    width: 100%;

    .content-top {
        height: 300px;
        background-image: url(../assets/img/jumbotron.jpg);
        background-size: cover;
        position: relative;

        button {
            color: white;
            font-size: 1.3rem;
            font-weight: 700;
            padding: 12px 12px;
            background-color: $primary;
            border: 1px solid $primary;
            position: absolute;
            bottom: -25px;
            left: 230px;
        }
    }

    .content-bottom {
        padding: 40px 0 20px 0;
        width: 70%;
        margin: 0 auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 20px;

        button {
            color: white;
            font-size: 0.7rem;
            font-weight: 700;
            padding: 7px 40px;
            background-color: $primary;
            border: 1px solid $primary;
            cursor: pointer;
        }
    }
}

.bottom {
    background-color: $primary;
    height: 150px;
    position: relative;
    z-index: 999;

    .features {
        width: 70%;
        height: 150px;
        margin: 0 auto;
        @include flex(center, center, stretch);

        ul {
            width: 100%;
            list-style: none;
            @include flex(center, center, row);
            gap: 20px;

            li {
                height: 150px;
                width: calc(100% / 5);
                @include flex(center, center, stretch);

                a {
                    text-decoration: none;
                    @include flex(center, center, stretch);


                    img {
                        height: 50px;
                    }
                }
                
                p {
                    color: white;
                    font-size: 0.80rem;
                    font-weight: 700;
                    padding-left: 10px;
                }
            }
        }
    }
}
</style>