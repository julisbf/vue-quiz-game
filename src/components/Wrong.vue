<template>
  <div class="alert alert-danger text-center">
    <h1>Oops! That's inorrect!</h1>
    <hr>
    <button class="btn btn-primary" @click="tryAgain">Try Again!</button>
  </div>
</template>
<script>
export default {
  methods: {
    tryAgain() {
      this.$emit('wrong');
    }
  }
}
</script>