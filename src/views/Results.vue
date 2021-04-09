<template>
  <div class="result-container">
    <div class=" result-box bg-white rounded-lg relative top-20 text-center">
      <div class="text-center w-5/12 mx-auto">
        <span class="iconify text-6xl text-center w-full" data-icon="emojione:trophy" data-inline="false"></span>
      </div>
      <p class="text-4xl mt-8 font-bold text-blue-900">{{resultText}}</p>
      <!-- <p class=" mt-2 font-bold text-blue-900">{{resultText}}</p> -->
      <p class="mt-4 text-3xl text-yellow-300"><span class="text-6xl text-yellow-300">{{correctAnswersCount * 5}}</span> pts</p> 
      <p class="mt-4 text-blue-900">You got <span :class="[correctAnswersCount > 5 ? 'text-green-500' : 'text-red-500', 'text-2xl']">{{correctAnswersCount}}</span> / <span class="text-2xl">{{totalQuestionsCount}}</span> correct answers</p>
      <div class="absolute bottom-6 border-solid border-2 border-blue-900 try px-3 py-2 bg-white rounded-md cursor-pointer btn">
        <p class="text-blue-900" @click="resetGame">try again</p>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'Results',
  computed : {
    correctAnswersCount(){
      return this.$store.state.score
    },
    totalQuestionsCount(){
      return this.$store.state.data.length 
    },
    resultText(){
      if(this.correctAnswersCount > 5){
        return 'Sports Guru!'
      }else if(this.correctAnswersCount == 5){
        return 'Kinda good'
      }else{
        return 'You no sabi!'
      }
    }
  },
  methods:{
    resetGame(){
      this.$store.dispatch('reset');
    }
  }

}
</script>
<style scoped>
.result-container{
  background-color: #6066D0 70%;;
}
.result-box{
  min-height: 63vh;
  width: 90%;
  margin: 0 auto;
  padding: 30px 20px;
  max-width: 500px;
}
.try{
  left: 40%
}
.btn:hover{
  background-color: rgba(30, 58, 138);
}
.btn:hover p{
  color: white
}
@media only screen and (min-width: 1024px) {
  .try{
    left: 42%
  }
  .result-box{
    min-height: 75vh
  }
}
</style>