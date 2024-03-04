<template>
  <div>
    <my-input label="price" v-model="price" ></my-input>
    <my-input label="shipping" v-model="shipping"></my-input>
    <my-input label="discount" v-model="discount"></my-input>
    <p>total cost: {{total}}</p>
  </div>
</template>

<script>


import MyInput from "@/components/MyInput.vue";

export default {
  components: {MyInput},
  data(){
    return{
      price: 0,
      shipping: 0,
      discount: 0
    }
  },
  computed:{
    total:function (){
      return Number(this.price) + Number(this.shipping) - Number(this.discount)
    }
  }

}
</script>

<style>

</style>
