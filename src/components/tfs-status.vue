<template>
    <div class="tfs-status">
        <p class="tfs-status-text">小树已经</p>
        <p class="meter-num">{{ meterNum }}</p>
        <p class="tfs-status-text">米高了！</p>
    </div>
    <div class="tfs-status">
        <p class="tfs-status-text">生长速度</p>
        <p class="speed-num">{{ growSpeed }}</p>
    </div>
</template>

<script>
export default {
    name: 'tfs-status',
    props: {
        meterNum: {
            type: Number,
            default: 0
        },
        growSpeed: {
            type: Number,
            default: 0
        }
    },
    data() {
        return {
            metersFontSize: '50px',
            speedFontSize: '50px'
        }
    },
    watch: {
        meterNum: function (val) {
            this.metersFontSize = '80px';
            setTimeout(() => {
                this.metersFontSize = '50px';
            }, 100);
        },
        growSpeed: function (val) {
            this.speedFontSize = '80px';
            setTimeout(() => {
                this.speedFontSize = '50px';
            }, 100);
        }
    }
}
</script>

<style>
.tfs-status {
    display: flex;
    justify-content: center;
    align-items: baseline;
}

.tfs-status-text {
    font-weight: 700;
    font-size: 25px;
}

.meter-num {
    font-family: Josefin Sans;
    font-weight: 800;
    font-size: v-bind(metersFontSize);
    margin: 0 10px;
    background-image: -webkit-linear-gradient(right,#96c93d, rgb(0, 176, 155));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: 0.5s;
}

.speed-num {
    font-family: Josefin Sans;
    font-weight: 800;
    font-size: v-bind(speedFontSize);
    margin: 0 10px;
    background-image: -webkit-linear-gradient(right,#a78800, rgb(95, 65, 0));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: 0.5s;
}
</style>