<template>
  <transition name ="slide">
    <div v-show="visible">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
  export default {
    name: 'carousel-slide',
    data () {
      return {
        index: 0
      }
    },
    computed: {
      visible () {
        return this.index === this.$parent.index
      }
    }
  }
</script>

<style>
.slide-enter-active{
  animation: slideIn 1.5s ease-in-out;
  }
.slide-leave-active{
  animation: slideOut 1.5s ease-in-out;
  position: absolute;
  top : 0;
  left: 0;
  right:0;
  width : 100%;
  }
@keyframes slideIn {
  from {transform: translateX(100%); }
  to {transform: translateX(0%); }
  }
@keyframes slideOut {
  from {transform: translateX(0%); }
  to {transform: translateX(-100%); }
  }
</style>
