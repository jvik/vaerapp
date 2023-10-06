<template>
    <div>
        <img v-bind:src="createUrl(beaufort)" alt="">
    </div>
</template>

<script>
export default {
    name: 'WindArrow',
    props: {
        beaufort: String,
    },
    data() {
        return {
            preurl: 'https://skodje.org/verdata/images/wb/BF'
        }
    },
    methods: {
        createUrl(test) {
            return this.preurl + test + '.svg'
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
