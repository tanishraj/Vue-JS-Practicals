<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Animations</h1>
        <hr>
        <button class="btn btn-primary" @click="show = !show">Show Alert</button>
        <br>
        <br>
        <transition name="slide">
        <div class="alert alert-info" v-if="show">This is some info.</div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      show: false,
    }
  }
}
</script>

<style>
  .slide-enter{
  }

  .slide-enter-active{
    animation: slide-in 1s ease-out forwards;
  }

  .slide-leave{
  }

  .slide-leave-active{
    animation: slide-out 1s ease-out forwards;
  }

  @keyframes slide-in {
    from{
      transform: translateY(20px);
      opacity: 0;
    }
    to{
      transform: translateY(0);
    }
  }

  @keyframes slide-out {
    from{
      transform: translateY(0);
    }
    to{
      transform: translateY(20px);
      opacity: 0;
    }
  }
</style>