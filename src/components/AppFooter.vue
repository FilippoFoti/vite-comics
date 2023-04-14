<script>
export default {
    name: "AppFooter",
    data() {
        return {
            linksFooter: {
                "DC COMICS": [
                    {
                        name: "Characters",
                        url: "#"
                    },
                    {
                        name: "Comics",
                        url: "#"
                    },
                    {
                        name: "Movies",
                        url: "#"
                    },
                    {
                        name: "TV",
                        url: "#"
                    },
                    {
                        name: "Games",
                        url: "#"
                    },
                    {
                        name: "Videos",
                        url: "#"
                    },
                    {
                        name: "News",
                        url: "#"
                    }
                ],
                "DC": [
                    {
                        name: "Terms Of Use",
                        url: "#"
                    },
                    {
                        name: "Privacy policy(New)",
                        url: "#"
                    },
                    {
                        name: "Ad Choices",
                        url: "#"
                    },
                    {
                        name: "Advertising",
                        url: "#"
                    },
                    {
                        name: "Jobs",
                        url: "#"
                    },
                    {
                        name: "CPSC Certificates",
                        url: "#"
                    },
                    {
                        name: "Subscriptions",
                        url: "#"
                    },
                    {
                        name: "Talent Workshops",
                        url: "#"
                    },
                    {
                        name: "Ratings",
                        url: "#"
                    },
                    {
                        name: "Shop Help",
                        url: "#"
                    },
                    {
                        name: "Contact Us",
                        url: "#"
                    }
                ],
                "SITES": [
                    {
                        name: "DC",
                        url: "#"
                    },
                    {
                        name: "MAD Magazine",
                        url: "#"
                    },
                    {
                        name: "DC Kids",
                        url: "#"
                    },
                    {
                        name: "DC Universe",
                        url: "#"
                    },
                    {
                        name: "DC Power Visa",
                        url: "#"
                    }
                ],
                "SHOP": [
                    {
                        name: "Shop DC",
                        url: "#"
                    },
                    {
                        name: "Shop DC Collectibles",
                        url: "#"
                    }
                ]
            },
            logoFooter: [
                {
                    img: "footer-facebook.png",
                    url: "#"
                },
                {
                    img: "footer-twitter.png",
                    url: "#"
                },
                {
                    img: "footer-youtube.png",
                    url: "#"
                },
                {
                    img: "footer-pinterest.png",
                    url: "#"
                },
                {
                    img: "footer-periscope.png",
                    url: "#"
                }
            ]
        }
    },
    methods: {
        getImgPath(name) {
            return new URL(`../assets/img/${name.img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <footer>
        <div class="top">
            <div class="left">
                <div class="list" v-for="(item, key) in linksFooter">
                    <h3>{{ key }}</h3>
                    <ul>
                        <li v-for="link in item">
                            <a :href="link.url">{{ link.name }}</a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="right">
                <img src="../assets/img/dc-logo-bg.png" alt="Logo">
            </div>
        </div>
        <div class="bottom">
            <div class="container">
                <div class="left">
                    <button>SING-UP NOW!</button>
                </div>
                <div class="right">
                    <ul>
                        <li>FOLLOW US</li>
                        <li v-for="item in logoFooter">
                            <a :href="item.url">
                                <img :src="getImgPath(item)" alt="Logo">
                            </a>    
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

footer {
    height: 350px;
    background-image: url(../assets/img/footer-bg.jpg);
    background-position: center;
    display: flex;
    align-items: center;
    flex-direction: column;
    .top {
        width: 70%;
        margin: 0 auto;
        display: flex;
        position: relative;
        .left {
            width: 35%;
            display: flex;
            flex-wrap: wrap;
            .list {
                width: calc(100% / 3);
                height: 60%;
            
                h3 {
                    color: white;
                    font-size: 1.1rem;
                    padding: 10px 0;
                }
                
                ul {
                    list-style-type: none;
                    
                    a {
                        color: rgba(149, 149, 149, 1);
                        font-size: 0.7rem;
                        text-decoration: none;
                    }
                }
            }
        }
        .right {
            position: absolute;
            right: 0;
            bottom: -17%;
            z-index: 0;

            img {
                width: 450px;
            }

        }
    }
    .bottom {
        width: 100%;
        background-color: rgba(48, 48, 48, 1);
        position: relative;

        .container {
            width: 70%;
            height: 100px;
            margin: 0 auto;
            @include flex(center, space-between, stretch);

            .left {
                button {
                    color: white;
                    font-size: 1rem;
                    font-weight: 700;
                    padding: 10px 10px;
                    background-color: rgba(48, 48, 48, 1);
                    border: 3px solid $primary;
                    cursor: pointer;
                }
            }

            .right {
                ul {
                    @include flex(center, center, stretch);
                    gap: 20px;
                    list-style-type: none;

                    li {
                        color: $primary;
                        font-size: 1rem;
                        text-decoration: none;
                        font-weight: 700;
                    }
                }
            }
        }
    }
}
</style>