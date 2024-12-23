<template>
    <div class="main-background-color container" style="position: relative;">
        <h2 class="title">ULTRANET</h2>
        <menu-list title="MENU" v-bind:datas="menuData"></menu-list>
        <menu-list title="YOUR FAVORITE" v-bind:datas="favoriteData"></menu-list>
        <follow></follow>        
    </div>
</template>

<script>
import Menu from './nav/nav_menu.vue';
import Follow from './nav/nav_follow.vue'
import menuJson from '@/resource/nav/menu.json';
import favoriteJson from '@/resource/nav/favorite.json';

export default {
    components: {
        'menu-list': Menu,
        'follow': Follow
    },
    data() {
        return {
            menuData: [],
            favoriteData: []
        }
    },
    methods: {
        loadMenu() {
            this.menuData = menuJson
        },
        loadFavorite() {
            this.favoriteData = favoriteJson
        }
    },
    created() {
        this.loadMenu()
        this.loadFavorite()
    }
}
</script>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
    }
    .title {
        color: white;
        font-size: 18px;
        text-align: center;
        line-height: 40px;
        letter-spacing: 2px;
    }
</style>