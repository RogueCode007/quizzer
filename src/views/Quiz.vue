<template>
<div class="quiz-container">
  <Timer :timeLeft="timeLeft" :timeLimit='timeLimit' />
  <div v-for="data in dataArr" :key="data.id">
    <Question :data="data" v-if="data.show" v-on:next="displayNext"/>
  </div>

</div>
</template>

<script>
import Timer from '@/components/BaseTimer.vue'
import Question from '@/components/Question.vue'
import { mapState } from 'vuex'
export default {
  name: 'Quiz',
  components:{
    Timer,
    Question
  },
  data() {
    return {
      timeLimit: 120,
      timePassed: 0,
      timerInterval: null,
      num: 0
    }
  },
  computed: {
    timeLeft() {
      return this.timeLimit - this.timePassed
    },
    ...mapState({
      dataArr: state => state.data,
    }),
  },
  methods:{
    startTimer() {
      this.timerInterval = setInterval(() => (this.timePassed += 1), 1000);
    },
    onTimesUp() {
      clearInterval(this.timerInterval);
      this.$router.push('./result');
    },
    displayNext(){
      if(this.num < this.dataArr.length - 1){
        console.log(this.num);
        this.dataArr[this.num].show = false
        this.num ++;
        this.dataArr[this.num].show = true
      }else{
        this.$router.push('/result');
      }

    }
  },
  watch: {
    timeLeft(newValue) {
      if (newValue === 0) {
        this.onTimesUp();
      }
    }
  },
  mounted() {
    this.startTimer();
  }, 
  
}
</script>

<style scoped>
.quiz-container{
  background: #6066D0 70%;
  max-width: 500px;
  margin: 0 auto
}
</style>