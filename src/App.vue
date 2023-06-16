<script setup lang="ts">
import { ref, onMounted } from "vue";
import { Chessground } from 'chessground/chessground';
//TODO: не работает нифига с этими стилями.
import '@/assets/chessground.base.css';
import '@/assets/chessground.brown.css';
import '@/assets/chessground.cburnett.css';
//С этим работает, но кривовато.
// import '@/assets/board.css';
const boardDiv = ref<HTMLElement | null>(null);

onMounted(() => {
    const config = {};
    if(boardDiv.value) {
      const ground = Chessground(boardDiv.value, config);
    }
  });
</script>

<template>
  <div ref="boardDiv"></div>
</template>

<style>
body {
  background-color: #222;
}
#boardDiv {
  width: 500px;
  height: 500px;
  }
</style>