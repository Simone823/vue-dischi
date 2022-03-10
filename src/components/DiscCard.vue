<template>

    <!-- Disc -->
    <div class="disc_card">
        <!-- Img wrapper -->
        <div class="img_wrapper">
            <img :src="poster" alt=""> 
        </div>

        <!-- Info wrapper card -->
        <div class="info_wrapper">
            <h3 class="title">{{title}}</h3>
            <h3 class="author">{{author}}</h3>
            <h3 class="year">{{year}}</h3>
        </div>

    </div>

</template>


<script>
export default {
    name: "DiscCard",  
    
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
    },
}
</script>



<style lang="scss" scoped>
@import "../assets/scss/common.scss";

.disc_card {
    width: calc(100% / 5 - 30px);
    height: 370px;
    background-color: $color-blue-turquoise;
    padding: 15px 0;
    flex-grow: 1;
    box-shadow: 0 0 8px black;

    .img_wrapper {
        width: 80%;
        margin: 0 auto;
        margin-bottom: 15px;
        box-shadow: 0 0 5px black;

        img {
            aspect-ratio: 1/1;
        }
    }

    .info_wrapper {
        text-align: center;
        color: $color-white;
        letter-spacing: 1px;
        width: 80%;
        margin: 0 auto;

        .title {
            text-transform: uppercase;
            margin-bottom: 15px;
            text-shadow: 0 0 5px black;
        }

        .author {
            color: $color-gray;
            font-size: 18px;
            margin-bottom: 5px;
            text-shadow: 0 0 5px black;
        }

        .year {
            color: $color-gray;
            font-size: 16px;
            text-shadow: 0 0 5px black;
        }
    }
}

</style>