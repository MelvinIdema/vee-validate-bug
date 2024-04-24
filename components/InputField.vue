<script setup>
const props = defineProps({
  modelValue: {
    type: [String],
    default: "",
  },
  name: String,
  rules: [String, Object, undefined]
})

const emit = defineEmits(['update:modelValue'])

const name = toRef(props, 'name')
const {
  value: inputValue,
  handleBlur,
  handleChange
} = useField(name, props.rules, { syncVModel: true })
</script>

<template>
  <div>
    <input 
      :name="name"
      :id="name"
      type="text"
      :value="inputValue"
      @input="handleChange"
      @blur="handleBlur"
    >
  </div>
</template>

<style scoped></style>
