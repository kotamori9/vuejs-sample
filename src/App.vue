<template>
  <div class="main">
    <button @click="show = !show">切り替え</button>
    <transition
     name="fade"
     appear
    >
      <p v-if="show">hello</p>
    </transition>
    <transition 
      name="slide" 
      type="animation"
      appear
    >
      <p v-show="show">bye</p>
    </transition>
  </div>
</template>


<script>
export default{
  data(){
    return{
      show:true
    };
  }
};
</script>


<style scoped>
.fade-enter{

  opacity: 0;
}
.fade-enter-active{

  transition: opacity 0.5s;
}
.fade-enter-to{

  opacity: 1;
}
.fade-leave{

  opacity: 1;
}
.fade-leave-active{

  transition: opacity 0.5s;
}
.fade-leave-to{

  opacity: 1;
}

.slide-enter,
.slide-leave-to{
  opacity: 0;
}
.slide-leave-active{
  animation: slide-in 0.5s;
  transition: opacity 1s;
}
.slide-leave-active{
  animation: slide-in 1s reverse;
}


@keyframes slide-in{
  from{
    transform: translateX(100px);
  }
  to{
    transform: translateX(0);
  }
}

.main{
  width:70%;
  margin: auto;
  padding: 5rem;
  text-align: center;
}
</style>