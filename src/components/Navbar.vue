<template>
<nav class="navbar navbar-expand-lg navbar-light px-10 py-5 justify-content-between bg-danger text-white">
  <a class="navbar-brand h1 text-white" href="#">EF-Commerce</a>
  

  <div class="d-flex gap-10">

      <i class="fa fa-shopping-cart" aria-hidden="true"></i>
      <i class="fa fa-user pl-5" aria-hidden="true"></i>
  </div>
</nav>
</template>

<script>
    export default{

    }
</script>

<style>
.navbar-brand{
  font-size: 30px;
}

@media(max-width: 414px){
  .navbar-brand{
    font-size: 20px;
    padding: 0px ;
  }
}

</style>