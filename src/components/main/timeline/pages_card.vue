<template>
    <div class="pages-container timeline-box">
        <div class="pages-title">
            Your pages
            <button class="pages-menu"></button>
        </div>
        <div>
            <person-entry 
                v-for="(contact, index) in pagesData"
                :name="contact.name"
                :img="contact.img"
                :status="true"
                :key="index">
            </person-entry>
        </div>
    </div>
</template>

<script>
import pagesJson from '@/resource/timeline/pages.json';
import personEntry from '@/components/social/person_entry.vue';
export default {
    data() {
        return {
            pagesData: []
        }
    },
    methods: {
        loadDatas() {
            this.pagesData = pagesJson
        }
    },
    created() {
        this.loadDatas()
    },
    components: {
        'person-entry': personEntry
    }
}
</script>

<style scoped>
.pages-container {
    padding: 20px;
}
.pages-title {
    display: flex;
    flex-direction: row;
    color: #5c5e6e;
    font-weight: 600;
    font-size: 18px;
    align-items: center;
    margin-bottom: 20px;
}
.pages-menu {
    background-color: #8f98a9;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    border: 0;
    padding: 0;
    margin-right: 8px;
    margin-left: auto;
    box-shadow: -8px 0 0 0 #8f98a9, 8px 0 0 0 #8f98a9;
    cursor: pointer;
}
</style>