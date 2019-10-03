<template>
  <form @submit.prevent="handleSubmit">
    <VTextInput
      v-model="text"
      placeholder="What needs to be done?"
    />
  </form>
</template>

<script>
import VTextInput from '@/components/atoms/VTextInput'

export default {
  components: { VTextInput },
  props: {
    preventEmptySubmit: { type: Boolean, default: false }
  },
  data () {
    return {
      text: ''
    }
  },
  methods: {
    handleSubmit () {
      if (!this.text && this.preventEmptySubmit) return

      this.$emit('submit', this.text)
      this.text = ''
    }
  }
}
</script>
