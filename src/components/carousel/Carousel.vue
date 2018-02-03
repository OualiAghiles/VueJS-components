<template>
<div class="carousel">
  <slot></slot>
  <button class="carousel__nav carousel__next btn btn-outline-secondary" @click.prevent="next">
    <i class="fa fa-chevron-right"></i>
  </button>
  <button class="carousel__nav carousel__prev btn btn-outline-secondary" @click.prevent="prev">
    <i class="fa fa-chevron-left"></i>
  </button>
</div>
</template>

<script>
  export default {
    name: 'carousel',
    data () {
      return {
        index: 0,
        slides: []
      }
    },
    mounted () {
      this.slides = this.$children
      this.slides.forEach((slide, i) => {
        slide.index = i
      })
    },
    computed: {
      slidesCount () { return this.slides.length }
    },
    methods: {
      next () {
        this.index++
        if (this.index >= this.slidesCount) {
          this.index = 0
        }
      },
      prev () {
        this.index--
        if (this.index < 0) {
          this.index = this.slidesCount - 1
          console.log(this.index)
        }
      }
    }
  }
</script>

<style>
.carousel{
  position:  relative;
  overflow: hidden;
  }
.carousel img {
  width : 100%;
  }
.carousel__nav{
  position: absolute;
  top : calc(50% - 10px);
  right: 10px;
  left: auto;
  }
.carousel__prev{
  left: 10px;
  }
</style>
