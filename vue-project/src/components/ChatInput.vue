<script setup>

import { ref, computed } from 'vue';
const emit = defineEmits(["test"])

const inputMessage = ref()
const props = defineProps(["message"])
const countMessage = props.message

const nombreMessage = computed(() => `Vous avez ${ countMessage } message`)

function sendMessages() {
    console.log(inputMessage.value)
    emit("test", {messageChat:inputMessage.value})
    inputMessage.value = ""
}

</script>

<template>
    <div class="bottomPosition">
        <p>{{ nombreMessage }}</p>
        <div class="flex">
            <input type="text" class="border-black border-2 text-black padding-input space-between" v-model="inputMessage" size="66">
            <button><img src="../assets/send.png" alt="sendingMessage" width="50px" @click="sendMessages"></button>
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