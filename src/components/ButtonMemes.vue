<template>
  <div>
    <button type="button" class="btn btn-success d-flex ms-auto me-auto mb-3" @click="onClick" :disabled="isDisabled">Click For The memes</button>
  </div>
</template>

<script>
export default {
  name : 'ButtonMemes',
  data() {
    return {
      isDisabled : false
    }
  },
  methods: {
    onClick() {
      this.$emit('termChange')
      this.isDisabled = true;
    }
  }
}
</script>

<style scoped>

input {
  width: 45%
}

</style>