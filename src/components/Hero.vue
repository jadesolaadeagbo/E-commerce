<template>
    <div class="heroContainer d-flex align-center">
        <div class="sideTexts d-block ml-10">
            <span class="mainheader h1">Welcome to EF-commerce</span><br>
            <span class="subheader h1 ">Super value deals</span><br>
            <span class="subheader h1">On all products</span><br>
            <span>Save more with coupons & get up to 70% off!</span>
        </div>
        
        <img src="../assets/woman.png" class="heroImg">
        
    </div>
</template>

<script>
    export default{

    }
</script>

<style>
.heroContainer{
    background-color: rgb(255, 226, 231);
    
}
.heroImg{
    width: 40%;
}
.mainheader{
    font-size: 56px;
}
 
@media(max-width: 768px){
    .mainheader{
        font-size: 24px;
    }
    .subheader{
        font-size: 24px;
    }
    .heroContainer{
    }
}

</style>