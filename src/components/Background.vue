<template>
    <div id="background" :style="{ 'background-image': `${backgroundUrl}` }">
        <div class="glass"/>
    </div>
</template>


<script>
export default {
    name: 'Background',
    created() {
        this.updateBackground();
        this.interval = setInterval(() => this.updateBackground(), 1000 * 60 * 60); //Check time every 1 hour
    },
    data() {
        return {
            backgroundUrl: '',
            images: {
                notime: require('../assets/day-summer.jpg'),
                sunrise: require('../assets/sunrise.jpg'),
                morning: require('../assets/morning.jpg'),
                afternoon: require('../assets/afternoon.jpg'),
                sunset: require('../assets/sunset.jpg'),
                night: require('../assets/night.jpg')
            }
        }
    },
    methods: {
        updateBackground() {
            var date = new Date();

            switch(true) {
                case date.getHours() < 6:
                    this.backgroundUrl = 'url(' + this.images.night + ')';
                    break;
                case date.getHours() < 9:
                    this.backgroundUrl = 'url(' + this.images.sunrise + ')';
                    break;
                case date.getHours() < 12:
                    this.backgroundUrl = 'url(' + this.images.morning + ')';
                    break;
                case date.getHours() < 17:
                    this.backgroundUrl = 'url(' + this.images.afternoon + ')';
                    break;
                case date.getHours() < 20:
                    this.backgroundUrl = 'url(' + this.images.sunset + ')';
                    break;
                case 20 <= date.getHours():
                    this.backgroundUrl = 'url(' + this.images.night + ')';
                    break;
                default:
                    this.backgroundUrl = 'url(' + this.images.notime + ')';
            }
        }
    }
}
</script>

<style scoped>
#background {
    background-attachment: fixed;
    position: absolute;
    width: 100%;
    height: 100%;
    background-size: cover;
    z-index: -1;
    overflow: hidden;
}

.glass {
    width: 100%;
    height: 100%;
    box-shadow: inset 0 0 2000px rgba(255, 255, 255, .2);
    background: inherit;
    filter: blur(5px);
    transform: scale(1.05);
}
</style>
