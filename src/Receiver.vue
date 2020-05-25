<template>
  <div id="app">
    <Caller />
  </div>
</template>

<script>
import EventBus from "./EventBus"
import Caller from './components/Caller.vue'

export default {
  name: 'Receiver',
  components: {
    Caller
  },
  methods: {
    Receive(v) {
      console.log('발신자가 '+v+'라고 말하네요.')
    }
  },
  created(){
    EventBus.$on('Call', parameter => {
        this.Receive(parameter)
    })
  }
}
</script>