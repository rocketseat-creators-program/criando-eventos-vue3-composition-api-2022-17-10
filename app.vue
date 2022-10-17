<template>
  <div>
    <SubscriptionForm 
      @subscribe="onSubscribe"  
      @subscribe:user="onSubscribeUser"
    />
    <SubscriptionForm2
      @subscribe="onSubscribe"  
      @subscribe:user="onSubscribeUser"
    />
    <SubscriptionForm3
      @subscribe="onSubscribe"  
      @subscribe:user="onSubscribeUser"
    />
  </div>
</template>

<script lang="ts" setup>

function onSubscribe() {
  console.log('send subscription')
}

function onSubscribeUser(value: string) {
  console.log(value)
}

</script>