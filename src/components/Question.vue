<template>
  <div class="question-box bg-white rounded-lg relative">
    <p class="text-lg font-bold question">{{data.question}}</p>
    <div v-for="(choice, index) in data.choices" :key="choice.id" :class="[{'selected': index == activeIndex}, {'correct': index == answerIndex && selected}, 'mt-6','border', 'border-solid', 'py-2', 'px-1', 'cursor-pointer']" @click.once="resolveAnswer(index)">
      <p class="choice">{{choice.choice}}</p>
    </div>
    <div class="absolute bottom-2 right-4 ">
      <p class="float-right border-solid border px-3 py-1 text-white bg-yellow-400 rounded-md cursor-pointer" @click="$emit('next')">Next</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data'],
  data(){
    return {
      selected: false,
      answerIndex: null,
      activeIndex: null,
      clicked: false,
      correct_choice: null
    }
  },
  methods:{
    resolveAnswer(index){
      if(!this.selected){
        this.selected = true;
        this.activeIndex = index;
      } 
      if(index == this.answerIndex){
        this.$store.commit('changeScore')
      }
    }
  },
  created(){
    this.data.choices.map((choice, index)=>{
      if(choice.is_correct_choice > 0){
        this.answerIndex = index
      }
      
    })
  }
}
</script>

<style>
.question-box{
  min-height: 63vh;
  width: 90%;
  margin: 40px auto;
  padding: 30px 20px;
}
.question, .choice{
  color: #2F527B;
}
.selected{
  background-color: #EA8282;
  color: white;
  transition: 0.5s
}
.selected p{
  color: white
}
.correct p{
  color: white
}
.correct{
  background-color: #60BF88;
  color: white;
  transition: 0.5s
}
@media only screen and (min-width: 1024px){
  .question-box{
    min-height: 75vh
  }
}
</style>