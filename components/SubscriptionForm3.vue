<template>
  <form @submit.prevent="subscribe">
    <label>Email
      <input v-model="email" type="email"/>
    </label>
    <button>Subscribe</button>
  </form>
</template>
    
<script lang="ts" setup>
interface ISubscriptionFormEmits {
    (e: 'subscribe'): void;
    (e: 'subscribe:user', email: string): void;
}

const emit = defineEmits<ISubscriptionFormEmits>()

const email = ref('') 

watch(email, () => {
    emit('subscribe:user', email.value)
})

function subscribe(): Event {
    emit('subscribe')
    return null
}
</script>