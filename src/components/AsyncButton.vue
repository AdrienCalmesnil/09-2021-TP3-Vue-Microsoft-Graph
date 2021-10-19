<template>
  <BaseButton :disabled="isDisabled" :color="color" @click.stop.prevent="handleClick"><slot></slot></BaseButton>
  <p v-if="isDisabled">Button disabled {{nbClick}} times</p>
</template>

<script>
import BaseButton from './BaseButton.vue'

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },

  data () {
    return {
      isDisabled: false,
      nbClick:0,
    }
  },

  methods: {
    handleClick () {

      var vm = this
      vm.nbClick++

      function promise_button() {
        return new Promise((disable_button) => {
          disable_button()
        })
      }

      function disable_button(){
        vm.isDisabled = true
        setTimeout(() => vm.isDisabled = false, vm.nbClick*1000)
      }

      const promise_result = promise_button()
      promise_result.finally(disable_button)

    }
  }
}
</script>

<style scoped></style>
