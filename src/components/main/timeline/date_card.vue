<template>
    <div class="date-container timeline-box">
        <div class="date-top-area">
            <img :src="imgUrl" class="date-img"/>
            <div class="date-text">
                <div class="date-text-month">Jan</div>
                <div class="date-text-day">01</div>
            </div>
        </div>
        <div class="date-bottom-season">
            Winter Wonderland
        </div>
        <div class="date-bottom-time">
            01st Jan, 2019 07:00AM
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            imgUrl: "https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
        }
    }
}
</script>

<style scoped>
.date-container {
    margin:20px 0;
    padding: 10px;
}
.date-top-area {
    position: relative;
}
.date-img {
    max-width: 100%;
    display: block;
    padding-bottom: 12px;
}
.date-text {
    position: absolute;
    top: 15px;
    left: 20px;
}
.date-text-month {
    background-color: #1687fa;
    padding: 7px 20px;
    border-radius: 4px 4px 0 0;
    color: #fff;
    font-weight: 600;
    font-family: "DM Sans", sans-serif;
    text-align: center;
}
.date-text-day {
    color: #fff;
    font-size: 22px;
    font-weight: 600;
    font-family: "DM Sans", sans-serif;
    text-align: center;
    padding: 6px 0;
    background-color: rgba(0, 0, 0, 0.4);
    backdrop-filter: blur(4px);
}
.date-bottom-season {
    font-family: "DM Sans", sans-serif;
    font-weight: 600;
    color: #c3c5d5;
    margin-bottom: 5px;
    padding: 0 14px;
}
.date-bottom-time {
    padding: 0 14px;
    font-family: "DM Sans", sans-serif;
    font-weight: 500;
    color: #5c5e6e;
    font-size: 13px;
}
</style>