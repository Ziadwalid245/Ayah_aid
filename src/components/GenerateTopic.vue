<script lang="ts">
export default {
  name:"Generatetopic",
  data() {
    return {
      buttonVisible:true,
      topicVisible:false,
      topic:"",
      numberArray:[] as number[]
    }
  },
  methods: {
    showTopic(){
    this.buttonVisible= false;
    this.topicVisible= true;
    this.generateTopic();
   }, 
    getTopic(){
      this.numberArray = Array.from({length:15}, (_, i) => (i+1))
      const randomIndex = Math.floor(Math.random() * this.numberArray.length );
      return this.numberArray[randomIndex]
      },
    generateTopic(){
    for (let i = 0; i <= this.numberArray.length; i++) {
     const randomTopic = this.getTopic();
      this.topic+=randomTopic;
    }

  }
    }
    
    }


    
</script>
<template>
  <button v-show="buttonVisible" @click="showTopic">Generate A Topic</button>
  <div v-show="topicVisible" class="generated-topic-container">
    <p>Your unique topic is: <span>{{topic}}</span></p>
    <p>(copy and paste this in the ntfy app)</p>
  </div>
</template>

<style>
button{
  font-size: 1rem;
  cursor:pointer;
  padding: 5px;
}
div p{
  text-align: center;
}
</style>
