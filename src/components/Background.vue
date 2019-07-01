<template>
    <div id="background" :style="{ 'background-image': `${backgroundUrl}` }">
        <div class="glass"/>
    </div>
</template>


<script>
import imageF from '../assets/day-summer.jpg';
export default {
    name: 'Background',
    created() {
        this.updateBackground();
        this.interval = setInterval(() => this.updateBackground(), 1000 * 60 * 60); //Check time every 1 hour
    },
    data() {
        return {
            backgroundUrl: 'url(' + imageF + ')'
        }
    },
    methods: {
        updateBackground() {
            
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
    box-shadow: inset 0 0 2000px rgba(255, 255, 255, .5);
    background: inherit;
    filter: blur(15px);
    transform: scale(1.05);
}
</style>
