<template>
    <div class="container main-background-color">
        <transition name="follow">
            <a 
                v-show="!isShowTwitter"
                class="common topLine" 
                target="_blank"
                @mouseover="appearTwitter(true)">
                <span class="follow-text">
                    <Icon icon="ic:baseline-wechat" :width="iconWidth" :height="iconWidth" inline="true" class="icon"/>
                    Find me on WeChat
                </span>
            </a>
        </transition>
        <transition name="twitter">
            <a 
                v-show="isShowTwitter"
                class="twitter" 
                @mouseout="appearTwitter(false)">
                <span class="twitter-text">
                    <Icon></Icon>
                    WeChat：Rabbit_Musclz
                </span>
            </a>
        </transition>
    </div>

</template>

<script>
import { Icon } from '@iconify/vue2';
export default {
    data() {
        return {
            iconWidth: 16,
            isShowTwitter: false
        }
    },
    methods: {
        appearTwitter: function (isAppear) {
            this.isShowTwitter = isAppear
        }
    },
    components: {
        Icon
    }
}
</script>

<style scoped>
.container {
    position: relative;
    color: white;
    height: 52px;
    width: 100%;
    margin-top: auto;   
    overflow: hidden;
    flex-shrink: 0;
}
.icon {
    margin-right: 8px;
    width: 16px;
    height: 16px;
}
.common {
    display: flex;
    padding: 0 20px;
    color: #5c5e6e;
    font-size: 14px;
    height: 100%;
    cursor: pointer;
}
.topLine {
    border-top: 1px solid rgb(39, 42, 58);
}
.follow-text{
    display: flex;
    flex-direction: row;
    align-content: normal;
    align-items: center;
}
.twitter {
    position: absolute;
    top: 0;
    color: #fff;
    width: 100%;
    height: 50px;
    background-color: #272a3a;
    cursor: pointer;
}
.twitter-text {
    display: flex;
    flex-direction: row;
    align-content: normal;
    align-items: center;
    font-size: 14px;
    height: 52px;
    padding: 0 30px;
}
.twitter-enter {
    transform: translateY(-20px);
}
.twitter-leave-to {
    transform: translateY(-52px);
}
.twitter-enter-active,
.twitter-leave-active {
    transition: all 0.3s ease;
}
.follow-enter,
.follow-leave-to {
    transform: translateY(30px);
}
.follow-enter-active,
.follow-leave-active {
    transition: all 0.3s ease;
}
</style>