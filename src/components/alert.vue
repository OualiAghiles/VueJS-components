<template lang="html">
  <transition name="slide-fade">
    <div class="ui message" :class="cls">
      <i class="close icon" @click.prevent="close"></i>
      <div class="header">
        {{ msgHeader }}
      </div>
      <p> {{ msgContent }}</p>
    </div>
  </transition>

</template>

<script>
export default {
  props: {
    cls: {
      type: [String]
    },
    msgHeader: String,
    msgContent: String
  },
  data () {
    return {}
  },
  methods: {
    close () {
      this.$emit('close')
    }
  }

}
</script>

<style lang="css">
.slide-fade-enter-active {
  transition: all .9s ease;
}
.slide-fade-leave-active {
  transition: all 1.8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(30px);
  opacity: 0;
}
</style>
