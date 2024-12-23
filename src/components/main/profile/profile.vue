<template>
    <div class="profile-container">
        <div class="profile-avatar">
            <img src="@/assets/avatar.jpeg" class="profile-img"/>
            <div class="profile-name">Zhang Zhe</div>
        </div>
        <img :src="backImageUrl" class="back-image" alt/>
        <div class="segment-container">
            <a v-for="(segment, index) in segmentDatas"
                :class="[{active: isActive(index)},'segment-item']"
                v-on:mouseover="segmentChoose(index)"
                v-on:mouseout="segmentChoose(null)"
                v-bind:key="index">
                {{ segment }}
            </a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            backImageUrl: "https://images.unsplash.com/photo-1508247967583-7d982ea01526?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2250&q=80",
            avatarUrl: "https://images.genius.com/2326b69829d58232a2521f09333da1b3.1000x1000x1.jpg",
            segmentDatas: [
                "Timeline",
                "About",
                "Friends",
                "Photos",
                "More"
            ],
            segmentIndex: 0
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
    }
}
</script>

<style scoped>
.profile-container {
    position: relative;
    height: 40vh;
    min-height: 250px;
    min-width: 350px;
    z-index: 1;

 &:before {
    content: "";
    width: 100%;
    height: 100%;
    position: absolute;
    z-index: -1;
    left: 0;
    top: 0;
    background-image: url("https://images.unsplash.com/photo-1508247967583-7d982ea01526?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2250&q=80");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    filter: blur(50px);
    opacity: 0.7;
}
}
.back-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    border-radius: 4px;
}
.profile-avatar {
    position: absolute;
    display: flex;
    flex-direction: row;
    align-items: center;
    bottom: 16px;
    left: 24px;
    z-index: 1;
}
.profile-img {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    border: 3px solid #151728;
    object-fit: cover;
}
.profile-name {
    color: #fff;
    font-weight: 600;
    font-size: 22px;
    margin-left: 24px;
    margin-bottom: 24px;
}
.segment-container {
    display: flex;
    position: absolute;
    bottom: 0;
    left: 0;
    flex-direction: row;
    padding-left: 200px;
    width: 100%;
    background-color: #151728;
    border-radius: 0px 0px 4px 4px;
}
.segment-item {
    color: #5c5e6e;
    padding: 20px 16px;
    cursor: pointer;
}
.active {
    color: #fff;
    background-color: #1b1d2e;
    border-bottom: 3px solid #1488fa;
}
</style>
