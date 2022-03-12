<template>


    <!-- Wrapper disc -->
    <div class="disc_wrapper">
    
        <DiscCard v-for="(element, index) in filterValue" :key="index"
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

            // Array oggetti discCard
            arrayDisc: [],
        }
    },

    props: {
        // Recupero valueRecuperato da app
        valueRecuperatoDaApp: String,
    },

    methods: {

        // Chiamata al server api
        chimataDiscCard: function() {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then(res => {
                console.log(res.data.response);
                this.arrayDisc = res.data.response;
            })
        },
    },

    computed: {
        // Filtra valueOption
        filterValue: function() {
            if (this.valueRecuperatoDaApp == "") {
                return this.arrayDisc;
            } 

            return this.arrayDisc.filter((element) => {
                const { genre } = element;
                return genre.toLowerCase().includes(this.valueRecuperatoDaApp.toLowerCase());

            })

        },
    },

    created() {
        this.chimataDiscCard();
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
    padding: 5px 20px;
    overflow-y: auto;
}

</style>