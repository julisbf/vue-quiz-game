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
        <transition name="bounce">
          <app-wrong v-show="isWrong" @wrong="isWrong = !isWrong"></app-wrong>
        </transition>
        <transition name="flip" mode="out-in">
          <component :is="mode" @answered="answered($event)" @confirmed="mode = 'app-question'"></component>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
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
<style>
.flip-enter-active {
  animation: flip-in 0.5s ease-out forwards;
}

.flip-leave-active {
  animation: flip-out 0.5s ease-out forwards;
}

.bounce-enter-active {
  -webkit-animation: bounce-in-top 1.1s both;
  animation: bounce-in-top 1.1s both;
}

.bounce-leave-active {
  -webkit-animation: bounce-out-top 1s both;
  animation: bounce-out-top 1s both;
}

@keyframes flip-out {
  from {
    transform: rotateY(0deg);
  }

  to {
    transform: rotateY(90deg);
  }
}

@keyframes flip-in {
  from {
    transform: rotateY(90deg);
  }

  to {
    transform: rotateY(0deg);
  }
}

@-webkit-keyframes bounce-in-top {
  0% {
    -webkit-transform: translateY(-500px);
    transform: translateY(-500px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
    opacity: 0;
  }
  38% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
    opacity: 1;
  }
  55% {
    -webkit-transform: translateY(-65px);
    transform: translateY(-65px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  72% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  81% {
    -webkit-transform: translateY(-28px);
    transform: translateY(-28px);
    -webkit-animation-timing-function: ease-in;
  }
  90% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  95% {
    -webkit-transform: translateY(-8px);
    transform: translateY(-8px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
}
@keyframes bounce-in-top {
  0% {
    -webkit-transform: translateY(-500px);
    transform: translateY(-500px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
    opacity: 0;
  }
  38% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
    opacity: 1;
  }
  55% {
    -webkit-transform: translateY(-65px);
    transform: translateY(-65px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  72% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  81% {
    -webkit-transform: translateY(-28px);
    transform: translateY(-28px);
    -webkit-animation-timing-function: ease-in;
  }
  90% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  95% {
    -webkit-transform: translateY(-8px);
    transform: translateY(-8px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
}
@-webkit-keyframes bounce-out-top {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  5% {
    -webkit-transform: translateY(-30px);
    transform: translateY(-30px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  15% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  25% {
    -webkit-transform: translateY(-38px);
    transform: translateY(-38px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  38% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  52% {
    -webkit-transform: translateY(-75px);
    transform: translateY(-75px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  70% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  85% {
    opacity: 1;
  }
  100% {
    -webkit-transform: translateY(-800px);
    transform: translateY(-800px);
    opacity: 0;
  }
}
@keyframes bounce-out-top {
  0% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  5% {
    -webkit-transform: translateY(-30px);
    transform: translateY(-30px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  15% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  25% {
    -webkit-transform: translateY(-38px);
    transform: translateY(-38px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  38% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  52% {
    -webkit-transform: translateY(-75px);
    transform: translateY(-75px);
    -webkit-animation-timing-function: ease-in;
    animation-timing-function: ease-in;
  }
  70% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
    -webkit-animation-timing-function: ease-out;
    animation-timing-function: ease-out;
  }
  85% {
    opacity: 1;
  }
  100% {
    -webkit-transform: translateY(-800px);
    transform: translateY(-800px);
    opacity: 0;
  }
}
</style>
