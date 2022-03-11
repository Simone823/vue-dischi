<template>

    <!-- Select wrapper -->
    <div class="select_wrapper">

        <!-- Select -->
        <select name="Select" id="select" v-model="valueSelect" @change="$emit('filtra', valueSelect)">
            <option value="" disabled selected hidden>Filtra per</option>
            <option value="metal">Metal</option>
            <option value="pop">Pop</option>
            <option value="rock">Rock</option>
            <option value="jazz">jazz</option>
        </select>

        <!-- Button -->
        <button @click="resetValueSelect()">Reset</button>

    </div>

</template>


<script>

export default {
    name: "SelectOption",

    data() {
        return {

            // Valore selezionato
            valueSelect: "",
        }
    },

    methods: {

        // Reset valore select option
        resetValueSelect: function() {
            this.valueSelect = "";
            console.log(this.valueSelect);
            this.$emit('filtra', this.valueSelect);
        },  
    }
}
</script>


<style lang="scss" scoped>
@import "../assets/scss/common.scss";

.select_wrapper {
    width: 100%;
    display: flex;
    justify-content: center;
    gap: 20px;

    select {
        max-width: 600px;
        min-height: 28px;
        flex-grow: 1;
        border: none;
        border-radius: 5px;
        background-color: $color-blue-turquoise;
        color: $color-white;
        padding-left: 10px;
        filter: drop-shadow(0 0 5px black);
    }

    button {
        text-transform: uppercase;
        padding: 5px 25px;
        border: none;
        cursor: pointer;
        border-radius: 5px;
        background-color: $color-red;
        color: $color-white;
        opacity: 0.65;
        filter: drop-shadow(0 0 5px black);

        &:hover {
            opacity: 1;
            transition: all 280ms linear;
        }
    }
}

</style>