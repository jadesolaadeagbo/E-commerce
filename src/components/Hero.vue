<template>
    <div class="heroContainer d-lg-flex d-md-flex align-center text-danger justify-content-around">
        <div class="sideTexts d-lg-block d-md-block ml-10">
            <span class="mainheader h1">AFFORDABLES</span><br>
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
        font-size: 39px;
    }
    .subheader{
        font-size: 20px;
    }
    .littleText{
        padding-top: 10px;
        font-size: 18px;
    }
    .heroImg{
        width: 50%
    }
}

@media(max-width: 414px){
    .heroContainer{
        
        padding-top: 50px;
        padding-bottom: 50px;
    }
    .heroImg{
        display:none
    }
    .mainheader{
        
    }
}

</style>