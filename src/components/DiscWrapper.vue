<template>

    <!-- Wrapper disc -->
    <div class="disc_wrapper">
        <DiscCard v-for="(element, index) in arrayDisc" :key="index"
            :poster="element.poster"
            :title="element.title"
            :author="element.author"
            :year="element.year"
        />

    </div>

</template>



<script>
import DiscCard from "./DiscCard.vue";

// Axios
import axios from 'axios';

export default {
    name: "DiscWrapper",
    components: {
        DiscCard,
    },

    data() {
        return {
            arrayDisc: [],
        }
    },

    methods: {
        chimataDiscCard: function() {

        },
    },

    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
        .then(res => {
            console.log(res.data.response);
            this.arrayDisc = res.data.response;
        })
    },
}
</script>



<style lang="scss" scoped>

.disc_wrapper {
    // border: 2px solid orange;
    max-width: 1168px;
    flex-grow: 1;
    display: flex;
    flex-wrap: wrap;
    row-gap: 20px;
    gap: 30px;
    padding: 0 20px;
    overflow-y: auto;
}

</style>