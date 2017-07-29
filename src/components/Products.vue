<template>
<div>
    <div id="product-header" class="container">
        <div style="border-left: 5px solid #F38D84; margin-left: 10px;" class="container">
            <div class="col-md-6"><h2>Top Products</h2></div>
            <div class="col-md-6 push-right" id="options">
                <label><input type="checkbox"> Men</label>
                <label><input type="checkbox"> Women</label>
                <label><input type="checkbox"> Unisex</label>
                <label><input type="checkbox"> All</label>  
                <button style="margin-left: 10px;" class="btn btn-primary">Get All Products</button>            
            </div>
        </div>
    </div> 
    <div class="container">
        <div class="row">
             <div class="row">
        <div class="row">
            <div class="col-md-9">
                <h3>Products</h3>
            </div>
            <div class="col-md-3">
                <!-- Controls -->
                <div class="controls pull-right hidden-xs">
                    <a class="left fa fa-chevron-left btn btn-success" href="#carousel-example"
                        data-slide="prev"></a><a class="right fa fa-chevron-right btn btn-success" href="#carousel-example"
                            data-slide="next"></a>
                </div>
            </div>
        </div>
        <div id="carousel-example" class="carousel slide hidden-xs" data-ride="carousel">
            <!-- Wrapper for slides -->
            <div class="carousel-inner">
                <div class="item active">
                    <div class="row">
                        <div class="col-sm-3" v-for="product in products">
                            <div class="col-item">
                                <div class="photo">
                                    <img :src="product.imageURL" class="img-responsive" :alt="product.productName" />
                                </div>
                                <div class="info">
                                    <h4 class="text-center">{{product.productName}}</h4>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data () {
        return {
            products: []
        }
    },
    created() {
        this.getProducts();
    },
    methods: {
        getProducts() {
            this.$http.get('https://us-central1-bookaholic-786.cloudfunctions.net/home')
            .then(response => {
                this.products = response.body.products;
            }, error => {
                console.log(error);
            });
        }
    }
}
</script>

<style scoped>
#product-header {
    padding: 25px;
    width: 100%;
    margin: 0px;
    background: #F3F3F3;
    color: #4E4E4E;
}

#options {
    margin-top: 25px;
}

label {
    margin: 7px;
}

@import url(http://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.min.css);
.col-item
{
    border: 1px solid #E1E1E1;
    border-radius: 5px;
    background: #FFF;
}
.col-item .photo img
{
    margin: 0 auto;
    width: 100%;
}

.col-item .info
{
    padding: 10px;
    border-radius: 0 0 5px 5px;
    margin-top: 1px;
}

.col-item:hover .info {
    background-color: #F5F5DC;
}
.col-item .price
{
    /*width: 50%;*/
    float: left;
    margin-top: 5px;
}

.col-item .price h5
{
    line-height: 20px;
    margin: 0;
}

.price-text-color
{
    color: #219FD1;
}

.col-item .info .rating
{
    color: #777;
}

.col-item .rating
{
    /*width: 50%;*/
    float: left;
    font-size: 17px;
    text-align: right;
    line-height: 52px;
    margin-bottom: 10px;
    height: 52px;
}

.col-item .separator
{
    border-top: 1px solid #E1E1E1;
}

.clear-left
{
    clear: left;
}

.col-item .separator p
{
    line-height: 20px;
    margin-bottom: 0;
    margin-top: 10px;
    text-align: center;
}

.col-item .separator p i
{
    margin-right: 5px;
}
.col-item .btn-add
{
    width: 50%;
    float: left;
}

.col-item .btn-add
{
    border-right: 1px solid #E1E1E1;
}

.col-item .btn-details
{
    width: 50%;
    float: left;
    padding-left: 10px;
}
.controls
{
    margin-top: 20px;
}
[data-slide="prev"]
{
    margin-right: 10px;
}

</style>
