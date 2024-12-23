<template>
    <div class="message-container timeline-box">
        <div class="message-info">
            <img src="@/assets/avatar.jpeg" class="message-info-img"/>
            <div>
                <div>
                    <strong>Zhang Zhe </strong>
                    create new 
                    <span>album</span>
                </div>
                <div class="message-info-subtitle">6 hours ago</div>
            </div>
            <button class="message-info-menu"></button>
        </div>
        <div class="message-content">
            <div>When the bass drops, so do my problems.</div>
            <div class="message-content-images">
                <img :src="leftImageUrl" class="message-conetent-image"/>
                <div class="message-right-images">
                    <img :src="rightFirstImageUrl" class="message-conetent-image"/>
                    <img :src="rightSecondImageUrl" class="message-conetent-image"/>
                </div>
            </div>
        </div>
        <div class="message-actions">
            <a class="message-action">
                <Icon :icon="loveIcon" inline="true" class="message-action-icon"/>
                87
            </a>
            <a class="message-action">
                <Icon :icon="chatIcon" inline="true" class="message-action-icon"/>
                20
            </a>
            <a class="message-action">
                <Icon :icon="forwardIcon" inline="true" class="message-action-icon"/>
                13
            </a>
        </div>
    </div>
</template>

<script>
import { Icon } from '@iconify/vue2';
export default {
    data() {
        return {
            leftImageUrl: 'https://images.unsplash.com/photo-1508179719682-dbc62681c355?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2378&q=80',
            rightFirstImageUrl: 'https://images.unsplash.com/photo-1502872364588-894d7d6ddfab?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2250&q=80',
            rightSecondImageUrl: 'https://images.unsplash.com/photo-1566737236500-c8ac43014a67?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80',
            loveIcon: 'mynaui:heart',
            chatIcon: 'mynaui:chat-dots',
            forwardIcon: 'mynaui:calendar-up'
        }
    },
    components: {
        Icon
    }
}
</script>

<style scoped>
.message-container {
    padding-top: 20px;
    margin-top: 20px;
}
.message-info {
    display: flex;
    border: none;
    padding: 0 20px;
    align-items: center;
    padding-bottom: 20px;
    flex-wrap: wrap;
}
.message-info strong {
    font-weight: bolder;
}
.message-info span {
    color: #1771d6;
    cursor: pointer;
}
.message-info-img {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    object-fit: cover;
    margin-right: 20px;
}
.message-info-menu {
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
    margin-bottom: auto;
    margin-top: 5px;
}
.message-info-subtitle {
    font-size: 15px;
    color: #595c6c;
    margin-top: 4px;
}
.message-content {
    padding: 0 20px 20px;
}
.message-content-images {
    display: flex;
    margin-top: 20px;
    max-height: 30vh;
}
.message-content-images > .message-conetent-image {
    width: 50%;
}
.message-right-images {
    display: flex;
    flex-direction: column;
    width: 50%;
    margin-left: 10px;
    line-height: 0;
}
.message-conetent-image {
    width: 100%;
    object-fit: cover;
    object-position: center;
    border-radius: 4px;
    margin-top: 10px;
}
.message-right-images > .message-conetent-image {
    height: calc(50%-10px);
}
.message-actions {
    padding: 0 20px 20px;
}
.message-action {
    display: inline-flex;
    align-items: center;
    text-decoration: none;
    color: #a2a4b4;
    font-weight: 600;
    margin-right: 20px;
    cursor: pointer;
}
.message-action:hover {
    color: #fff;
}
.message-action-icon {
    width: 16px;
    height: 16px;
    margin-right: 6px;
}
</style>