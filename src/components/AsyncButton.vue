<template>
  <BaseButton :disabled="isDisabled" :color="color" @click.stop.prevent="handleClick"><slot></slot></BaseButton>
  <p v-if="isDisabled" :icon="['fas', 'circle-notch']" pulse>Button disabled</p>
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
    }
  },

  methods: {
    handleClick () {

      var vm = this

      function promise_button() {
        return new Promise((disable_button) => {
          disable_button()
        })
      }

      function disable_button(){
        vm.isDisabled = true
        setTimeout(() => vm.isDisabled = false, 2000)
      }

      const promise_result = promise_button()
      promise_result.finally(disable_button)

    }
  }
}
</script>

<style scoped></style>
