<template>
<div>
    <div id="myCarousel" class="carousel slide" data-ride="carousel">
        <!-- Wrapper for slides -->
        <div class="carousel-inner" role="listbox">
            <!-- V-For Cursoul -->
            <div class="item active" v-for="slide in slides">
                <img class="img-responsive" :src="slide.imageURL" alt="Chania">
                <div class="carousel-caption">
                    <h1>Chania</h1>
                    <p>The atmosphere in Chania has a touch of Florence and Venice.</p>
                </div>
            </div>
        <!-- Left and right controls -->
        <a class="left carousel-control" href="#myCarousel" role="button" data-slide="prev">
            <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
            <span class="sr-only">Previous</span>
        </a>
        <a class="right carousel-control" href="#myCarousel" role="button" data-slide="next">
            <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
            <span class="sr-only">Next</span>
        </a>
    </div>
</div>
</div>
</template>

<script>
export default {
    data() {
        return {
            slides: []
        }
    },
    created() {
        this.getSlides();
    },
    methods: {
        getSlides() {
            this.$http.get('https://us-central1-bookaholic-786.cloudfunctions.net/home')
            .then(response => {
                this.slides = response.body.combos;
            }, error => {
                console.log(error);
            });
        }
    }
}
</script>

<style scoped>
.carousel .item {
  height: 590px;
}

.item img {
    position: absolute;
    top: 0;
    left: 0;
    min-height: 590px;
}

.carousel-caption {
    z-index: 1;
    text-align: center;
    top: 30%;
    bottom: auto;
    opacity: 0.9;
}
</style>
