<script>

export default {
    data() {
        return {
            return: {
                // termine da cercare
                term: "",
            }
        }
    },
    props: {
        title: String,
    },
    emits: ['search'],
};
</script>

<template>
    <header>
        <div class="nav-head container-fluid">
            <div class="row">
                <div class="col">
                    <nav class="navbar bg-body-tertiary">
                        <div class="container-fluid">
                            <!-- cambiare in logo succ.... -->
                            <a class="navbar-brand">{{ title }}</a>
                            <form class="d-flex" role="search" @submit.prevent="$emit('search', term)">

                                <input v-model="term" class="form-control me-2" type="search"
                                    placeholder="Search movies or tv series" aria-label="Search">



                                <button class="btn btn-outline-success" type="submit" @click="$emit('search', term)">
                                    Search
                                </button>
                            </form>
                        </div>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped></style>