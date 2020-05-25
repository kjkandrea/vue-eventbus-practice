<template>
  <div>
    <button @click="call">Receiver에게 말해요.</button>
  </div>
</template>

<script>
import EventBus from "../EventBus"

export default {
  name: 'Caller',
  methods: {
    call(){
      const argument = '바보';
      EventBus.$emit('Call', argument);
    },
  }
}
</script>