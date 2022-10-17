<template>
  <form @submit.prevent="subscribe">
    <label>Email
      <input v-model="email" type="email"/>
    </label>
    <button>Subscribe</button>
  </form>
</template>
  
<script lang="ts" setup>
const emit = defineEmits(['subscribe:user', 'subscribe'])

const email = ref('') 

watch(email, () => {
  emit('subscribe:user', email.value)
})

function subscribe(): Event {
  emit('subscribe')
  return null
}
</script>