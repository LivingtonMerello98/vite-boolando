<script>
//importo componenti

import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import AppMain from './components/AppMain.vue';

export default {
    //aggiunta componenti --> nomi
    components: {
        AppHeader,
        AppFooter,
        AppMain
    }
}

</script>


<template>
    <AppHeader />
    <AppMain />
    <AppFooter />
</template>


<style lang="scss" scoped></style>

