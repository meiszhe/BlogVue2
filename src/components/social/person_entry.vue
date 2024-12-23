<template>
    <div class="person-root">
        <!-- 头像 -->
        <img class="avatar" :src="img"/>
        <!-- 在线 -->
        <div v-if="isShowStatus" class="status"></div>
        <!-- 名字时间 -->
        <div class="name-time-box">
            <div :class="['name', {'name-center': time == ''}]">{{ name }}</div>
            <div class="time">{{ time }}</div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isShowTime: true,
            isShowStatus: true
        }
    },
    props: {
        name: {
            type: [String],
            default: ''
        },
        time: {
            type: [String],
            default: ''
        },
        img: {
            type: [String],
            default: ''
        },
        status: {
            type: Boolean,
            default: false
        }
    },
    created() {
        this.isShowStatus = this.status
    }

}
</script>

<style scoped>
.person-root {
    position: relative;
    overflow: hidden;
    margin-top: 18px;
    cursor: pointer;
}
.avatar {
    display: block;
    float: left;
    width: 45px;
    height: 45px;
    border-radius: 50%;
    border: 2px solid #e2b96c;
    margin-right: 20px;
    object-fit: cover;
    object-position: center;
}
.name-time-box {
    float: left;
}
.name {
    font-size: 15px;
    color: #ccc8db;
}
.name-center {
    margin-top: 15%;
}
.time {
    font-size: 15px;
    color: #595c6c;
}
.status {
    position: absolute;
    background-color: #7fd222;
    border-radius: 50%;
    width: 8px;
    height: 8px;
    right: 0;
    top: 0;
    bottom: 0;
    margin-top: auto;
    margin-bottom: auto;
}

</style>