<script>
// import MyComponent from "./components/MyComponent.vue";
import CatalogList from '../components/CatalogList.vue'

export default {
    data() {
        return {
            title: "Hello world"
        }
    },

    components: {
        //   MyComponent,
        CatalogList
    },
};
</script>

<template>
    <CatalogList />
</template>

<style lang="scss" scoped></style>