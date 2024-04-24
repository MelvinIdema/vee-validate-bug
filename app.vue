<script setup>
import * as Yup from 'yup'

function handleSubmit(values) {
  console.log(values);
}

const email = ref('test@test.')
</script>

<template>
  <Form @submit="handleSubmit">
    <label for="email"> Email: </label>
    <InputField 
      v-model="email"
      name="email"
      :rules="Yup.string().email().required()"
    />
    <ErrorMessage name="email" />
    <button type="submit">Submit</button>
  </Form>
</template>
