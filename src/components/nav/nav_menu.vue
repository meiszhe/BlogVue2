<template>
    <div class="common">
        <h2 class="menuText">{{ title }}</h2>
        <a v-for="(menu, index) in datas"
            :class="[{over : hoverIndex == index}, 'entry']" 
            v-on:mouseover="mouseStatus(index)" 
            v-on:mouseout="mouseStatus(null)" 
            :key="index">
            <Icon :icon="menu.icon" :width="iconWidth" :height="iconWidth" inline="true" class="icon"/>
            <span>{{ menu.name }}</span>
        </a>
    </div>
</template>


<script>
import { Icon } from '@iconify/vue2';
export default {
    data() {
        return {
            iconWidth: 16,
            hoverIndex: null
        }
    },
    methods: {
        mouseStatus(index) {
            this.hoverIndex = index == null ? null : index
        }
    },
    props: {
        title: {
            type: [String],
            default: ''
        },
        datas: []
    },
    components: {
        Icon
    }
}

</script>

<style scoped>
.common{
    padding: 30px;
    padding-left: 50px;
    color: #5c5e6e;
    background-color: rgb(22, 22, 35);
}
.menuText{
    font-size: 17px;
    font-weight: 600;
    margin-bottom: 20px;
}
.entry {
    display: flex;
    font-size: 15px;
    line-height: 18px;
    margin-bottom: 20px;
    cursor: pointer;
}
.icon {
    margin-right: 16px;
    width: 16px;
    height: 16px;
}
.over {
    color: white;
}
</style>