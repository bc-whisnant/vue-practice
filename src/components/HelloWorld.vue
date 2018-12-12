<template>
  <div class="hello">
    <p>{{ msg }} {{ name }}</p>
    <h3>Hobbies</h3>
    <ul>
      <li v-for="(interest,index) in interests" :key="index">{{ interest }}</li>
    </ul>
    <ul>

      <li v-for="(stat, index) in stats" :key="index">{{ index }}: {{ stat }}</li>
    </ul>

    <button v-on:click="increment">+</button>
    <p>{{ count }}</p>
    <button v-on:click="decrement">-</button>
    <br>
    <br>
    <form action="" @keydown.enter.prevent.self>
      <input type="text" v-on:keyup.enter="addInputValue" v-on:keyup.backspace="count = 0">
    </form>
    

   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return {
      msg: 'Hello',
      name: 'Brandon',
      interests: [
        'programming', 'napping', 'petting gregg'
      ],
      stats: {
        Name: 'Brandon Whisnant',
        Profession: 'Software Developer',
        Age: 26
      },
      count: 0
    }
  },
  methods: {
    increment() {
      this.count += 1
     
    },
    decrement() {
      this.count -= 2
    },
    addInputValue(event) {
      this.value = event.target.value
      this.count += this.value
      this.count = parseInt(this.count)
    }
  }  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  li {
    list-style: none;
    padding: 10px;
    display: inline-block;
  }

</style>
