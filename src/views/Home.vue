<template>
  <div class="home">
  <h1>Home</h1>
  <h2>Refs</h2>
  <p>{{ alexOne.name }} - {{ alexOne.age }}</p>
  <button @click="updateAlexOne">Update Alex One</button>
  <h2>Reactive</h2>
  <p>{{ alexTwo.name }} - {{ alexTwo.age }} - {{ nameTwo }}</p>
  <button @click="updateAlexTwo">Update Alex Two</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'



export default {
  name: 'Home',
  setup() {
    
    const alexOne = ref({ name: 'Lewis', age: 44 })
    const alexTwo = reactive({ name: 'George', age: 63 })
    
    const nameOne = ref('mario')
    const nameTwo = reactive('luigi')
    

    const updateAlexOne = () => {
      alexOne.value.age = 35
    }

    const updateAlexTwo = () => {
      alexTwo.age = 25
      nameTwo = 'Mario'
    }

    return { updateAlexOne, alexOne, alexTwo, updateAlexTwo, nameTwo }
  },
}
</script>
