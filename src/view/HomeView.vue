<script setup>
import { ref, onBeforeMount, reactive } from 'vue';
let cruz = ref(false);
let cara = ref(false);

const img = document.getElementById("img");
let imageSrc = ref("src/assets/suerte2.jpg");

function setTimeOut() {
   setTimeout(caraCruz, 1500);
   imageSrc.value = ("https://media3.giphy.com/media/W12WAzuqod9VS/giphy.gif?cid=790b761156106ddeec3c204137667de386416c00eb45fcd1&rid=giphy.gif&ct=g")
   
}
let result = ref("");

const caraCruz = () =>{
    let random =  Math.floor(Math.random()*2 +1)
    if(random === 1){
        imageSrc.value = ("src/assets/lobo.jpg");
        result.value = "CARA";
    } else{
        imageSrc.value = ("src/assets/cruz.jpeg")
        result.value = "CRUZ";

    } 
}

</script>

<template>
<main> 
        <h1>¿Cara o Cruz?</h1>
        <h2>BUENA SUERTE!</h2>
        <p v-if="result">Ha salido {{ result }}!</p>
    <div>
        <img :src="imageSrc" id="img" >
        <button @click="setTimeOut">LANZAR</button>        
    </div>


</main>
</template>

<style scoped lang="scss">
main{
    height: 100vh;
    background: url("https://images.pexels.com/photos/7130474/pexels-photo-7130474.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1");
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: sans-serif;

    h2{
        margin-bottom:1em;
    }

    p{
        margin-bottom: .3em;
        font-size: 3em;
        font-weight: bold;
        color: black;
    }

    div{
        height: 20em;
        width: 20em;
        // background:red;
        position: relative;

        img{
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }
        img:nth-child(1){
            border-radius: 0;
        }

        button{
            // position: absolute;
            // bottom:0;
            width: 100%;
            height: 3em;
            background: blue;
            color:white;
            cursor: pointer;

            &:hover{
                opacity: .7;
            }
        }
    }

}
</style>