<template>
    <div class="heroContainer d-flex align-center text-danger justify-content-around">
        <div class="sideTexts d-block ml-10">
            <span class="mainheader h1 text-capitalize">AFFORDABLE FASHION</span><br>
            <span class="subheader h1 ">Super value deals on all products</span><br>
            <p class="littleText">Save more with coupons & get up to 70% off!</p>
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
    font-size: 72px;
}
.littleText{
    padding-top:20px;
    font-size: 24px;
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