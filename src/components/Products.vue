<template>
    <div class="wholecard card" >
  <img class="card-img-top" src="../assets/shoe.jpg" alt="Card image cap">
  <div class="card-body">
    <span class="d-flex justify-content-between align-items-center">
        Product 1
        <i class="fa fa-heart" aria-hidden="true"></i>
    </span>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. </p>

    <span class="d-flex justify-content-between align-items-center">
        <span>
            <i class="fa fa-star" aria-hidden="true"></i>
            5 Reviews
        </span>
        <span class="h3">€50</span>
    </span>

    <span>
        <button class="addtocart bg-success">Add to cart</button>
    </span>
   </div>
    </div>
</template>

<script>
export default{
    data(){

    }
}
</script>

<style>
.wholecard{
    width: 30%;
}
.card-img-top{
    width: 100%;
    height: 300px;
}
.addtocart{
    padding: 10px 7px;
    cursor: pointer;
    border-radius:8px;
}

@media(max-width: 768px){
    .wholecard{
        width: 48%;
    }
}
</style>