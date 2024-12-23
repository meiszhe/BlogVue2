<template>
    <div class="intro-container timeline-box">
        <div class="intro-title">
            Introduction
            <button class="intro-menu"></button>
        </div>
        <div class="intro-info">
            <div 
                v-for="(item, index) in datas" 
                v-bind:key="index" 
                class="intro-info-item">
                <Icon :icon="item.icon" inline="true" class="icon"/>
                {{ item.itemName }}
                <a href="#">{{ item.itemValue }}</a>
            </div>
        </div>
    </div>
</template>

<script>
import { Icon } from '@iconify/vue2';
export default {
    data() {
        return {
            datas: [
                {
                    itemName: "Product Designer at",
                    itemValue: "Bravebist",
                    icon: "mingcute:album-2-line"
                },
                {
                    itemName: "Live in",
                    itemValue: "Beijing",
                    icon: "mingcute:align-bottom-line"
                },
                {
                    itemName: "Player name",
                    itemValue: "Zhangzhe",
                    icon: "mingcute:baby-line"
                }
            ]
        }
    },
    components: {
        Icon
    }
}
</script>

<style scoped>
.intro-container {
    padding: 20px;
    font-size: 15px;
}
.intro-title {
    display: flex;
    flex-direction: row;
    color: #5c5e6e;
    font-weight: 600;
    font-size: 18px;
    align-items: center;
    margin-bottom: 20px;
}
.icon {
    display: inline-block;
    margin-right: 10px;
    width: 16px;
    height: 16px;
}
.intro-menu {
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
.intro-info {
    color: #c3c5d5;
}
.intro-info-item {
    display: flex;
    align-items: center;
}
.intro-info-item + .intro-info-item {
    margin-top: 14px;
}
.intro-info a {
    color: #1771d6;
    margin-left: 6px;
    text-decoration: none;
}
</style>