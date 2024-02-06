<script setup>

import { ref } from 'vue';
import ChatInput from '@/components/ChatInput.vue';
import ChatList from '@/components/ChatList.vue';
const messageChat = ref(["Ah"])

function addMessagetoList(payload) {
    console.log(payload)
    messageChat.value.push(payload.messageChat)
}

</script>

<template>
<h1 class="text-center text-5xl">Welcome to this chat</h1>
<div>
    
    <ChatList :message="messageChat" />
    <ChatInput :message="messageChat.length" @test="addMessagetoList"/>
</div>
</template>