<template>
  <div>
    <VCheckbox
      :value="value"
      @input="e => $emit('input', e)"
    />
    <VLabel
      :text="label"
      :strike-through="value"
    />
  </div>
</template>

<script>
import VCheckbox from '@/components/atoms/VCheckbox'
import VLabel from '@/components/atoms/VLabel'

export default {
  components: { VCheckbox, VLabel },
  props: {
    label: { type: String, required: true },
    value: { type: Boolean, required: true }
  }
}
</script>
