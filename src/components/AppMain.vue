<script>
// import ProductsData from '../assets/data/db.json'
import AppCard from './AppCard.vue';
export default {
    name: 'Main',
    components: {
        AppCard
    }

}
</script>


<template>
    <main class="py-120">
        <div class="container">
            <div class="row">
                <AppCard />
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables' as vars;
@use '../assets/styles/partials/mixin' as mixin;


main {
    padding-top: 120px;

    .container {
        max-width: 1200px;
        margin: 30px auto;
    }

}
</style>