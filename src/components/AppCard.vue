<template>
  <a :href="app.url" target="_blank">
    <img :src="require('../assets/icons/' + app.name + '.svg')" :alt=app.name>
  </a>
</template>

<script>

export default {
    name: 'AppCard',
    components: {
        
    },
    data() {
        return {
        }
    },
    props: {
        app: Object,
    },
}
</script>

<style scoped>
    a {
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0 20px;
        height: 50px;
        width: 50px;
        /* background: green; */
    }

    img {
        height: 80%;
        transition: 0.2s ease;
        filter: brightness(0) invert(1) opacity(0.7);
    }

    img:hover {
        transition: 0.2s ease;
        height: 90%;
        filter: brightness(0) invert(1) opacity(1);
    }

</style>