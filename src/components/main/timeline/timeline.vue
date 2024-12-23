<template>
    <div class="timeline-container">
        <div class="timeline-left">
            <introduction></introduction>
            <date-card></date-card>
            <pages></pages>
        </div>
        <div class="timeline-right">
            <share></share>
            <message></message>
        </div>
    </div>
</template>

<script>
import shareCard from './share_card.vue';
import introductionCard from './introduction_card.vue';
import pagesCard from './pages_card.vue';
import dateCard from './date_card.vue';
import messageCard from './message_card.vue';

export default {
    data() {
        return {

        }
    },
    components: {
        'share': shareCard,
        'introduction': introductionCard,
        'pages': pagesCard,
        'date-card': dateCard,
        'message': messageCard
    }
}
</script>

<style scoped>
.timeline-container {
    display: flex;
    padding-top: 20px;
    position: relative;
    z-index: 2;
}
.timeline-left {
    width: 310px;
    flex-shrink: 0;
}
.timeline-right {
    flex-grow: 1;
    padding-left: 20px;
}
</style>
