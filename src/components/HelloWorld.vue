<script setup>
import { ref } from 'vue'
import { inject, onMounted } from 'vue';

const toast = inject('toast');

// this works
function showToast (type) {
  toast.show(`This is the ${type} type toast.`, {
    type: type,
    duration: false,
  });
}

// this does not work
function clear() {
  toast.clear();
}

defineProps({
  msg: String
})

</script>

<template>
  <h1>{{ msg }}</h1>
  <button class="btn btn-stealth" @click="showToast('default')">
    Default
  </button>
  <button class="btn btn-primary" @click="showToast('primary')">
    Primary
  </button>
  <br/>
  <br/>
  <button class="btn" @click="clear">Clear Toasts</button>

</template>

<style scoped>
a {
  color: #42b983;
}
</style>
