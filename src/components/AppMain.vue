<script>
export default {
    name: "AppMain",
    data() {
        return {
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
            <div class="content">
                <h2> --> Content goes here &lt;-- </h2>
            </div>
        </div>
        <div class="bottom">
            <div class="features">
                <ul>
                    <li v-for="image in features">
                        <a :href="image.url">
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
    background-color: black;
    height: 130px;

    .content {
        width: 70%;
        height: 130px;
        margin: 0 auto;
        @include flex(center, start, row);

        h2 {
            font-size: 1.7rem;
            color: white;
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