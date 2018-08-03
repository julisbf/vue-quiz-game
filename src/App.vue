<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1 class="text-center">The Super Quiz</h1>
      </div>
    </div>
    <hr>
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <app-wrong v-show="isWrong" @wrong="isWrong = !isWrong"></app-wrong>
        <component :is="mode" @answered="answered($event)" @confirmed="mode = 'app-question'" v-show="!isWrong"></component>
      </div>
    </div>
  </div>
</template>

<script>
    import Question from './components/Question.vue';
    import Answer from './components/Answer.vue';
    import Wrong from './components/Wrong.vue';

    export default {
        data() {
            return {
              mode: 'app-question',
              isWrong: false
            }
        },
        methods: {
          answered(isCorrect) {
              if (isCorrect) {
                this.mode = 'app-answer';
              } else {
                this.isWrong = !this.isWrong;
                //this.mode = 'app-question';
                
                  //alert('Wrong, try again!');
              }
          }
        },
        components: {
            appQuestion: Question,
            appAnswer: Answer,
            appWrong: Wrong
        }
    }
</script>