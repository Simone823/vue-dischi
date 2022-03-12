<template>


    <!-- Wrapper disc -->
    <div class="disc_wrapper">
    
        <!-- SelectOption -->
        <SelectOption @filtra="recuperoValue"/>

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
import SelectOption from './SelectOption.vue';

export default {
    name: "DiscWrapper",
    components: {
        DiscCard,
        SelectOption,
    },

    data() {
        return {

            // Array oggetti discCard
            arrayDisc: [],
            
            // Recupero valueSelect
            valueRecuperato: "",
        }
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

        // Recupero valueSelect
        recuperoValue: function (valueSelect) {
            this.valueRecuperato = valueSelect;
            console.log(this.valueRecuperato);
        },
    },

    computed: {
        // Filtra valueOption
        filterValue: function() {
            if (this.valueRecuperato === "") {
                return this.arrayDisc;
            } 

            return this.arrayDisc.filter((element) => {
                const { genre } = element;
                return genre.toLowerCase().includes(this.valueRecuperato.toLowerCase());

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