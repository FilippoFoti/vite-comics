<script>
export default {
    name: "AppHeader",
    data() {
        return {
            links: [
                {
                    text: "CHARACTERS",
                    url: "#",
                    current: false
                },
                {
                    text: "COMINCS",
                    url: "#",
                    current: true
                },
                {
                    text: "MOVIES",
                    url: "#",
                    current: false
                },
                {
                    text: "TV",
                    url: "#",
                    current: false
                },
                {
                    text: "GAMES",
                    url: "#",
                    current: false
                },
                {
                    text: "COLLECTIBLES",
                    url: "#",
                    current: false
                },
                {
                    text: "VIDEOS",
                    url: "#",
                    current: false
                },
                {
                    text: "FANS",
                    url: "#",
                    current: false
                },
                {
                    text: "NEWS",
                    url: "#",
                    current: false
                },
                {
                    text: "SHOP",
                    url: "#",
                    current: false
                }
            ]
        }
    }
}
</script>

<template>
    <header>
        <div class="left">
            <a href="">
                <img src="../assets/img/dc-logo.png" alt="">
            </a>
        </div>
        <nav class="right">
            <ul class="header-nav">
                <li v-for="link in links" :class="link.current ? 'active' : ''">
                    <a :href="link.url">{{ link.text }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

header {
    width: 60%;
    height: 130px;
    margin: 0 auto;
    @include flex(center, space-between, row);

    ul {
        list-style: none;
        @include flex(center, center, row);

        li {
            margin: 0 5px;
            color: $text-color;
            height: 130px;
            line-height: 130px;


            a {
                color: inherit;
                text-decoration: none;
                font-weight: 700;
                font-size: 0.75rem;

                &:hover {
                    color: $primary;
                }
            }

            &.active {
                color: $primary;
                border-bottom: 5px solid $primary;
            }
        }
    }

}
</style>