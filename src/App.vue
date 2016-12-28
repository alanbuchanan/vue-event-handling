<template>
  <div>
    <button @mouseenter="counter += 1">Increment the count!</button>
    <button @click="increment()">Increment using a method!</button>
    <div v-text="counter"></div>
    <form @submit.prevent="logName()">
      <input @keyup.ctrl.alt.shift.down="keyHandler()" v-model="firstName" placeholder="First name..." />
    </form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        counter: 0,
        firstName: ''
      }
    },

    methods: {
      increment() {
        console.log('counter incremented!')
        this.counter += 1
      },

      logName() {
        console.log('firstName:', this.firstName)
      },

      keyHandler() {
        this.firstName = 'Evan'
      }
    }
  }
</script>