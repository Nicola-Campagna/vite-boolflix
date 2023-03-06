<script>
// import MyComponent


export default {
    name: "Header",
    data() {
        return {

        }
    },

    components: {
        //   MyComponent,
    },
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
                            <a class="navbar-brand">BOOLFIX</a>
                            <form class="d-flex" role="search">
                                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                                <button class="btn btn-outline-success" type="submit">Search</button>
                            </form>
                        </div>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped></style>