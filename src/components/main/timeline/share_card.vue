<template>
    <div class="share-container timeline-box">
        <div class="share-segment">
            <a 
                v-for="(segment, index) in segments"
                :class="[{active: isActive(index)}]"
                v-on:mouseover="segmentChoose(index)"
                v-on:mouseout="segmentChoose(null)"
                v-bind:key="index"
                href="#">
                {{ segment }}
            </a>
        </div>
        <div class="share-text">
            <img src="@/assets/avatar.jpeg" class="share-text-img"/>
            <textarea class="share-text-area" placeholder="Write something to Zhang Zhe.."></textarea>
        </div>
        <div class="share-item">
            <a 
                v-for="(option, index) in shareOptions"
                class="share-item-action"
                v-bind:key="index">
                <Icon :icon="option.icon" inline="true" class="share-item-action-icon"/>
                {{ option.name }}
            </a>
            <button class="share-button">
                Share
            </button>
        </div>
    </div>
</template>

<script>
import { Icon } from '@iconify/vue2';
export default {
    data() {
        return {
            segmentIndex: 0,
            segments: [
                "Status",
                "Photos",
                "Videos"
            ],
            shareOptions: [
                {
                    name: "People",
                    icon: "twemoji:baby"
                },
                {
                    name: "Check in",
                    icon: "twemoji:beach-with-umbrella"
                },
                {
                    name: "Mood",
                    icon: "twemoji:boy-medium-light-skin-tone"
                }
            ]
        }
    },
    methods: {
        segmentChoose(index) {
            this.segmentIndex = index == null ? 0 : index
        },
        isActive(index) {
            if (index == 0) {
                return true
            }
            return this.segmentIndex == index
        }
    },
    components: {
        Icon
    }
}
</script>

<style scoped>
.share-segment {
    display: flex;
    flex-direction: row;
    padding: 20px;
    align-items: center;
}
.share-segment a {
    color: #ccc8db;
    font-weight: 500;
    line-height: 0.7;
    cursor: pointer;
    padding: 10px 14px;
    border-radius: 20px;
    text-decoration: none;
}
.share-segment a + a {
    margin-left: 10px;
}
.active {
    background-color: #2e2e40;
    color: #fff;
}
.share-text {
    display: flex;
    flex-direction: row;
    padding: 0 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid #272a3a;
}
.share-text-img {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    object-fit: cover;
    margin-right: 20px;
}
.share-text-area {
    flex-grow: 1;
    background-color: transparent;
    border: none;
    resize: none;
    margin-top: 15px;
    color: #fff;
    max-width: calc(100% - 70px);
}
.share-item {
    display: flex;
    flex-direction: row;
    padding: 10px 20px;
}
.share-item-action {
    display: flex;
    align-items: center;
    text-decoration: none;
    color: #ccc8db;
    margin-right: 20px;
    cursor: pointer;
}
.share-item-action-icon {
    width: 16px;
    height: 16px;
    flex-shrink: 0;
    margin-right: 8px;
}
.share-button {
    background-color: #1B86F8;
    margin-left: auto;
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    color: #fff;
    box-shadow: 0 0 20px #1b86f9;
    cursor: pointer;
}
</style>