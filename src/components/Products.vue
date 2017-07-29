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

    </div>
</div>
</template>

<script>
export default {
  
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
</style>
