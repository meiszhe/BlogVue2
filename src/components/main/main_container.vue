<template>
    <div class="main-content">
        <profile></profile>
        <timeline></timeline>
    </div>
</template>

<script>
import profile from './profile/profile.vue';
import timeline from './timeline/timeline.vue';

export default {
    data() {
        return {

        }
    },
    components: {
        profile,
        timeline
    }
}
</script>

<style scoped>
.main-content {
    padding: 20px;
    flex-grow: 1;
    background-color: #24273b;
    overflow: auto;
}

</style>
