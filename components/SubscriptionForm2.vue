<template>
    <form @submit.prevent="subscribe">
        <label>Email
            <input v-model="email" type="email"/>
        </label>
        <button>Subscribe</button>
    </form>
</template>
    
<script lang="ts" setup>
const emit = defineEmits<{
    (e: 'subscribe'): void;
    (e: 'subscribe:user', email: string): void;
    (e: 'subscribe:user:test', id: number,  name: string): void;
}>()

const email = ref('') 

watch(email, () => {
    emit('subscribe:user', email.value)
})

function subscribe(): Event {
    emit('subscribe')
    emit('subscribe:user:test', 1, 'ash')
    return null
}
</script>