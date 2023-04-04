<template>
     <div class="products d-flex flex-wrap justify-content-between">
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
        <Products/>
    </div>

    </template>


<script> 
    import axios from 'axios';
    import Products from "./Products.vue";

    export default{
        name: "ProductsContainer",
        components:{
            Products,
        },
        data(){
            return {
                res: [],
            }
        },

        mounted() {
            axios.get("https://fakestoreapi.com/products").then((response) =>{
                console.log(response);
                this.res = JSON.stringify(response.data);
            }).catch((errors) =>{
                console.log(errors)
            })
            
        },

    }

</script>

<style>
.products{
    padding-top: 30px;
    width: 90%;
    margin: auto;
    padding-bottom: 30px;
    gap: 50px;
}

@media(max-width: 768px){
    .products{
        gap:20px
    }
}
</style>