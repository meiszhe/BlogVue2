<template>
    <div class="main-container">
        <search-bar></search-bar>
        <main-container></main-container>
    </div>
</template>

<script>
import searchBar from './main/search_bar.vue';
import mainContainer from './main/main_container.vue';

export default {
    data() {
        return {
            
        }
    },
    components: {
        'search-bar': searchBar,
        'main-container': mainContainer
    }
}
</script>

<style scoped>
@import url(@/assets/styles/main/main.css);
.main-container {
    display: flex;
    flex-direction: column;
    background-color: #181d2f;
    height: 100vh;
}

</style>