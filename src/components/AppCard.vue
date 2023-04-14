<script>
export default {
    name: "AppCard",
    props: {
        thumb: String,
        series: String
    }
}
</script>

<template>
    <div class="card">
        <figure>
            <img :src="thumb" alt="Copertina">
        </figure>
        <h2>{{ series }}</h2>
    </div>

</template>

<style scoped lang="scss">
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card {
    width: calc(100% / 6 - 20px);

    figure {
        height: 200px;

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
    
    }
    h2 {
        padding-top: 10px;
        font-size: 0.9rem;
        text-align:start;
        color: white;
        font-weight: 400;
    }
}
</style>