<script setup>
    import { ref } from 'vue'
    const count = ref(0)
    console.log(count) // { value: 0 }
console.log(count.value) // 0
    
</script>


<template>
    <h3>count {{ count }}</h3>
    <button @click="count++">aumentar</button>
    <button @click="count--">restar</button>

</template>