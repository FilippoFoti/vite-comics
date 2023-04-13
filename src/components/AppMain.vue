<script>
export default {
    name: "AppMain"
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
                    <li>
                        <div class="logo">
                            <img src="../assets/img/buy-comics-digital-comics.png" alt="DIGITAL COMICS">
                        </div>
                        <p>DIGITAL COMICS</p>
                    </li>
                    <li>
                        <div class="logo">
                            <img src="../assets/img/buy-comics-merchandise.png" alt="DC MERCHANDISE">
                        </div>
                        <p>DC MERCHANDISE</p>
                    </li>
                    <li>
                        <div class="logo">
                            <img src="../assets/img/buy-comics-subscriptions.png" alt="SUBSCRIPTION">
                        </div>
                        <p>SUBSCRIPTION</p>
                    </li>
                    <li>
                        <div class="logo">
                            <img src="../assets/img/buy-comics-shop-locator.png" alt="COMIC SHOP LOCATOR">
                        </div>
                        <p>COMIC SHOP LOCATOR</p>
                    </li>
                    <li>
                        <div class="logo">
                            <img src="../assets/img/buy-dc-power-visa.svg" alt="DC POWER VISA">
                        </div>
                        <p>DC POWER VISA</p>
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
        @include flex(center, center, none);

        ul {
            width: 100%;
            list-style: none;
            @include flex(center, center, row);
            gap: 20px;

            li {
                height: 150px;
                width: calc(100% / 5);
                @include flex(center, center, none);

                .logo {

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