<script>
export default {
  data() {
          return {
            count: 10,
            incrementAmount: 2,
            counterTitle: 'Counter Standard',
            message: 'Hello it works!@',
            listOfNumbers: [1, 2, 3, 4, 5]
          }
        },
        computed: {
          displayTitle() {
            if(this.count > 20) {
              return 'Counter Standard - Very Long'
            } else {
              return 'Counter Standard'
            }
          },
          optimizeIncrementAmount() {
            return this.displayTitle.length * this.incrementAmount
          }
        },
        methods: {
          incrementCount() {
            this.count += this.optimizeIncrementAmount
          }
        },
}
</script>

<template>
      <h1>{{ displayTitle }}</h1>
      <p>{{ optimizeIncrementAmount }}</p>
      <p>{{ count }}</p>
      <!-- @click === v-on:click (@ replaces v-on) -->
      <button v-on:click="incrementCount" >Increment Count</button>
      <div>
        <label for="incrementAmount">Increment By:</label>
        <input type="number"
          v-model="incrementAmount" />
      </div>
      
      <hr />
      <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
      <p v-else>Odd: {{ message }}</p>
      <ul>
        <li v-for="number in listOfNumbers" :key="`item-${index}`">{{ number * Math.random() }}</li>
      </ul>
</template>
