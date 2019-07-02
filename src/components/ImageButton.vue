<template>
    <div id="icon-button" :style="{ width: this.$props.width,
                                    height: this.$props.height,
                                    backgroundColor: this.$props.tint}">
        <i class="material-icons">{{ icon }}</i>
    </div>
</template>

<script>
export default {
    name: 'ImageButtonWidget',
    props: {
        icon: String,
        tint: String,
        width: String,
        height: String
    }
}
</script>

<style scoped>
#icon-button {
    cursor: pointer;
    margin: 20px auto;
    opacity: 0.8;
    background: inherit;
    transition: all .15s ease-in-out;
    
}

#icon-button:hover {
    opacity: 1;
    transform: scale(1.1);
    transition: all .15s ease-in-out;
}
</style>
