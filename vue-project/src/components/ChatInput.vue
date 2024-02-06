<script setup>

import { ref, computed } from 'vue';

const inputMessage = ref()
const messageChat = ref([])

const nombreMessage = computed(() => `Vous avez ${ messageChat.value.length } message`)

function sendMessage() {
    console.log(inputMessage.value)
    messageChat.value.push(inputMessage.value)
    inputMessage.value = ""
}

</script>

<template>
    <div class="margin">    
        <div v-for="item in messageChat" class="flex flex-col">
            <p>Pric Eorcq </p>
            <p> {{ item }}</p>
        </div>
    </div>
    <div class="bottomPosition">
        <p>{{ nombreMessage }}</p>
        <div class="flex">
            <input type="text" class="border-black border-2 text-black padding-input space-between" v-model="inputMessage" size="66    ">
            <button><img src="../assets/send.png" alt="sendingMessage" width="50px" @click="sendMessage"></button>
        </div>
    </div>
</template>

<style scoped>

.bottomPosition {
    position:absolute;
    bottom: 20px; 
    left: 33%;
}

.padding-input {
    padding: 5px;
}

.margin {
    margin: 15px;
}

.space-between {
    margin-right: 15px;
}

</style>