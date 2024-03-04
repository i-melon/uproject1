<template>
  <div class="item">
    <label>{{label}}</label>
    <input :value="modelValue" @input="send">
  </div>
</template>

<script>
export default {
  props:{
    label:[String],
    modelValue:[Number]
  },
  methods:{
    send(event){
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style scoped>
</style>