<template>

    <!-- <div v-if="loading">
             <div class="wave">
                    <div v-for="i in 20" :key='i' class="wave-inner" :id="i">
                    </div>
                </div>
            </div> -->

    <div class="result">
        <div class="result-inner">
            <h1>
                Personality Type
            </h1>
            <h2>{{Object.values(result)[0]}}</h2>
            <button @click="$router.push('/')" class="back">
                Home
            </button>
        </div>
    </div>

</template>
<script>
import axios from 'axios';
export default {
    name: 'resullt-section',
    props:["answers"],
    data(){
        return{
            result:"",
        }
    },
    beforeRouteLeave(to, from) {
        const answer = window.confirm('Do you really want to leave? you have unsaved changes!')
        if (!answer) return false
    },

    beforeRouteEnter(to,from,next){
        var s=""
        for (let i = 0; i < Object.values(to.params)[0].length;i++){
           s+=Object.values(to.params)[0][i];
        }
        console.log(s);
        axios.get("https://personality-test-zayed.herokuapp.com/getPersonality/" + s)
            .then(res => {
        next(vm => {
                vm.result = res.data;
            })
        }).catch(err => {
                console.log(err);
     })
        
    },
     methods:{
        //  wave(){
        //  const k = document.getElementsByClassName('wave-inner');
        //  for (let i = 0; i < k.length; i++) {
        //      k[i].style.animation = 'wave 1s ease-in-out infinite';
        //      k[i].style.animationDelay = i * 0.1 + 's';
        //      k[i].style.backgroundColor = "turquoise";
        //  }

        //  }
     }
}
</script>
<style>



.back{
    background-color:#5CDB95;
    width:100px;
    color:#EDF5E1;
    font-size:1.5rem;
    height:60px;
    border:none;
    border-radius:5px;
}

.wave {
    background-image: linear-gradient(to right, #f6d365 0%, #fda085 51%, #f6d365 100%);
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

.wave-inner {
    width: 10px;
    height: 10vh;
    margin: 10px;
}
@keyframes wave {
    0% {
        transform: translateY(0) scale(1);

        /* transform: rotate(0deg); */
    }

    25% {
        transform: translateY(-100px) scale(0);

        /* transform: rotate(90deg); */
    }

    50% {
        transform: translateY(0) scale(1);

        /* transform: rotate(0deg); */
    }

    75% {
        transform: translateY(100px) scale(0);

        /* transform: rotateX(90deg); */
    }

    100% {
        transform: translateY(0) scale(1);

        /* transform: rotate(0deg); */
    }

}
.result{
    display:flex;
    justify-content: center;
    align-items: center;
    flex-direction:column;
    width:100%;
    height:85vh;
    background-color: #05386B;
  
}
.result h1{
    color: #EDF5E1;
    font-size: 50px;
    
}
.result h2{
    color: #EDF5E1;
    font-size: 30px;
}
.result-inner{
    height:75vh;
    display:flex;
    flex-direction:column;
    justify-content:space-evenly;
    align-items:center;
}
</style>
