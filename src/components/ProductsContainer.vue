<template>
    
    <div class="products d-flex flex-wrap " >
        <div class="wholecard card" v-for="product in res" v-bind:key="product.id">
            <img class="card-img-top" v-bind:src="product.image" alt="Card image cap">
            <div class="card-body">
                <span class="d-flex justify-content-between align-items-center">
                    {{product.title}}
                    <i class="fa fa-heart" aria-hidden="true"></i>
                </span>

                <span class="d-flex justify-content-between align-items-center">
                    <span>
                        <i class="fa fa-star" aria-hidden="true"></i>
                        {{product.rating.rate}} Reviews
                    </span>
                    <span class="h3">€ {{product.price}}</span>
                </span>

                <span class="d-flex justify-content-between align-items-center mt-3">                           

                        <!-- <form>
                            <select class="border opt" >
                                <option value="1"> 1 </option>
                                <option value="2"> 2 </option>
                                <option value="3"> 3 </option>
                                <option value="4"> 4 </option>
                                <option value="5"> 5 </option>
                                <option value="6"> 6 </option>
                                <option value="7"> 7 </option>
                                <option value="8"> 8 </option>
                                <option value="9"> 9 </option>
                                <option value="10"> 10 </option>
                                <option value="11"> 11</option>
                                <option value="12"> 12</option>
                                <option value="13"> 13</option>
                                <option value="14"> 14</option>
                                <option value="15"> 15</option>
                                <option value="16"> 16</option>
                                <option value="17"> 17</option>
                                <option value="18"> 18</option>
                                <option value="19"> 19</option>
                                <option value="20"> 20</option>
                            </select>
                        </form> -->
                        
                        <form>
                    <select class="border"  ><!-- v-model="quant" -->
                        
                        <option v-bind:key="quantity"
              v-for="quantity in quantityArray"
              :value="quantity" class="opt">{{  quantity }}</option>
                    </select>                    
                </form>
                    <button class="addtocart bg-danger text-white" @click="addToCart(id)">Add to cart</button>
                </span>
                
            <!-- <p>This is a p tag: {{ quant }}</p> -->
                
            </div>
    </div>
    </div>
    </template>

<script> 
    import axios from 'axios';

    export default{
        name: "ProductsContainer",
        data(){
            return {
                res: [],
                products:[],
                cart: null,
                selected: 1,
                quantityArray:[],
                quant: '',
            }
        },

        mounted() {
            this.fetchProducts();
            this.incrementQuantity();

        },
        methods: {
            fetchProducts(){
                axios.get("https://fakestoreapi.com/products").then((response) =>{
                console.log(response);
                this.res = response.data;
            }).catch((errors) =>{
                console.log(errors)
            })
            },
            incrementQuantity(){
                for (let i = 1; i <= 20; i++) {
                this.quantityArray.push(i);
                }

                if (this.quantity > 1) {
                this.selected = this.quantity;
                }
            },
            addToCart(id){
                axios.post('https://fakestoreapi.com/carts',{
                    products:[{productId: id,quantity:this.quant}]
                }).then((response) => {
                    console.log(response)
                    localStorage.setItem('cart', response.data.id)
                } )
            },
            checkCart(){
                let item = localStorage.getItem('cart')
                
            }
        },

    //      methods:{                addToCart (id) {
    //   let data = {
    //     id: id,
    //     status: true
    //   }
    //   this.$store.commit('addToCart', id);
    //   this.$store.commit('setAddedBtn', data);
    // },
    // removeFromCart (id) {
    //   let data = {
    //     id: id,
    //     status: false
    //   }
    //   this.$store.commit('removeFromCart', id);
    //   this.$store.commit('setAddedBtn', data);
    // },
    // saveToFavorite (id) {
    //   let isUserLogged = this.$store.state.userInfo.isLoggedIn;

    //   if (isUserLogged) {
    //     this.$store.commit('addToFavourite', id);
    //   } else {
    //     this.$store.commit('showLoginModal', true);
    //   }
    // },
    // removeFromFavourite (id) {
    //   this.$store.commit('removeFromFavourite', id);
    // },
    // onSelectQuantity (id) {
    //   let data = {
    //     id: id,
    //     quantity: this.selected
    //   }
    //   this.$store.commit('quantity', data);
    // }
    // }
            
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

.opt{
    padding: 20px;
}
select{
    appearance: none;
}
.wholecard{
    width: 30%;
    height: 500px;
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
    .products{
        gap:20px
    }
    .wholecard{
        width: 48%;
    }
}

@media(max-width: 414px){

    .wholecard{
        width: 100%;
    }
}
</style>