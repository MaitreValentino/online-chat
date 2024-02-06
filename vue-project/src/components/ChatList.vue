<script setup>
const props = defineProps(["message"])

const messages = props.message
</script>

<template>
    <div class="margin">    
        <div v-for="item in messages" class="flex flex-col">
            <p>Pric Eorcq </p>
            <p> {{ item }}</p>
        </div>
        
    </div>
</template>