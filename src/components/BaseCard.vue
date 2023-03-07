
<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
    data() {
        return {
        }
    },
    props: {
        title: String,
        originalTitle: String,
        lang: String,
        vote: Number
    },
    methods: {
        getFlag(country) {
            country = country.toUpperCase();
            return "https://flagsapi.com/" + country + "/flat/64.png"
        }
    }


};
</script>

<template>
    <ul class="col">
        <li>
            <img :src="getFlag(lang)" alt="">
            <!-- {{ film.original_language }} -->
        </li>
        <li>TITOLO ORIGINALE: {{ originalTitle }}</li>
        <li>TITOLO: {{ title }}</li>
        <li>VOTO. {{ vote }}</li>
    </ul>
</template>

<style lang="scss" ></style>