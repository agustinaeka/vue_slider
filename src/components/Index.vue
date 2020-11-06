<template>
    <div class="wrapper">
     
        <div v-for="(color, index) in colors" :key="color" >
           <transition name="fade">
           <div  v-if="currentSlide == index" class="sliders" :class="color"></div>
            </transition>
        </div>
       
       
       
    </div>
    
    
 

</template>

<script>
export default {
  name: 'Index',
  data(){
    return{
      currentSlide : '',
      colors:["red","green","blue","yellow", "purple"]
    }
   
  },
  mounted(){
      
     setInterval(()=>{
       if(this.currentSlide == this.colors.length - 1){
         this.currentSlide = 0
       }else{
          this.currentSlide++
       }
    
        },1500)
    }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



.red{
  background-color: red;
   height: 500px;
  width: 100vw;
  position: absolute;

}

.blue{
  background-color: blue;
   height: 500px;
  width: 100vw;
    position: absolute;
  

}

.yellow{
  background-color: yellow;
   height: 500px;
  width: 100vw;
    position: absolute;

}

.green{
  background-color: green;
   height: 500px;
  width: 100vw;
    position: absolute;
}

.purple{
  background-color: purple;
   height: 500px;
  width: 100vw;
    position: absolute;
}


.dot{
  display: flex;
  justify-content: center;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 1s ease;
}

.fade-enter-from{
  opacity: 0;
  transform: translateX(-100%);
}
.fade-leave-to {
  opacity: 0;
  transform: translateX(100%);
}




</style>
