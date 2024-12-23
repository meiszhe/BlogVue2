<template>
    <div class="main-background-color" style="overflow: auto;">
        <div class="container">
            <h2 class="first-title">STORIES</h2>
            <person-entry
                v-for="(story, index) in storiesData" 
                :name="story.name" 
                :time="story.time" 
                :img="story.img" 
                :key="index">
            </person-entry>
        </div>
        
        <div class="container">
            <h2 class="first-title">CONTACTS</h2>
            <person-entry 
                v-for="(contact, index) in contactsData"
                :name="contact.name"
                :img="contact.img"
                :status="true"
                :key="index">
            </person-entry>
        </div>
    </div>
</template>

<script>
import PersonEntry from "./social/person_entry.vue";
import storiesJson from "@/resource/social/stories.json";
import contactsJson from "@/resource/social/contacts.json";

export default {
    components: {
        'person-entry': PersonEntry
    },
    data() {
        return {
            storiesData: [],
            contactsData: []
        }
    },
    methods: {
        loadStories() {
            this.storiesData = storiesJson
        },
        loadContacts() {
            this.contactsData = contactsJson
        }
    },
    created() {
        this.loadStories()
        this.loadContacts()
    }
}
</script>

<style scoped>
.container {
    padding: 30px;
    border-bottom: 1px solid #272a3a;
}

</style>