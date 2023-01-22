<script setup>
import { ref, onBeforeMount, reactive } from 'vue';

let imageSrc = ref("https://img.ecartelera.com/noticias/45400/45447-m.jpg");
let result = ref("");
let cara = ref(0);
let cruz = ref(0);

function setTimeOut() {
   setTimeout(caraCruz, 1500);
   imageSrc.value = ("https://media3.giphy.com/media/W12WAzuqod9VS/giphy.gif?cid=790b761156106ddeec3c204137667de386416c00eb45fcd1&rid=giphy.gif&ct=g")
}

const caraCruz = () =>{
    let random =  Math.floor(Math.random()*2 +1)
    if(random === 1){
        imageSrc.value = ("https://images.ecestaticos.com/mR_I6LnJXu_3a1t0i-bnnD8ZcsU=/0x0:0x0/1200x900/filters:fill(white):format(jpg)/f.elconfidencial.com%2Foriginal%2F108%2Fbb2%2Fcbd%2F108bb2cbd984f087cad9e0d71440fa6d.jpg");
        result.value = "CARA";
        cara.value++
    } else{
        imageSrc.value = ("https://i.blogs.es/e2031a/lobo/840_560.jpeg")
        result.value = "CRUZ";
        cruz.value++
    } 
}

</script>

<template>
<main> 
        <h1>¿Cara o Cruz?</h1>
        <h2>BUENA SUERTE!</h2>
        <p v-if="result" class="result">Ha salido {{ result }}!</p>
    <div>
        <img :src="imageSrc" id="img" >
        <button @click="setTimeOut">LANZAR</button>        
    </div>

    <p>Cara: {{ cara }}</p>
    <p>Cruz: {{ cruz }}</p>

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

    .result{
        margin-bottom: .3em;
        font-size: 3em;
        font-weight: bold;
        color: black;
    }

    p{
        font-size: 1.5em;
    }

    div{
        height: 20em;
        width: 20em;
        margin-bottom: 4em;

        img{
            width: 100%;
            height: 100%;
        }

        button{
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