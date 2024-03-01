<template>
  <div>
    <textarea :class="{red:!howManyLost}" v-model="message" @input="check"></textarea>
    <p>{{ howManyLost.toString() + '/' + limit.toString()}}</p>

  </div>
</template>

<script>

export default {
  data(){
    return{
      message: 'string',
      limit: 50,
      key: false
    }
  },
  computed:{
    howManyLost:function(){
      return this.limit - this.message.length
    },
    limitedMessage:function (){
      return this.message.substring(0,51)
    }
  },
  methods:{
    check(){
      if (this.howManyLost<0){
        this.message = this.message.substring(0,this.limit)
        this.key = true
      }
    }
  }
}
</script>

<style>
.red{
  border: red solid 2px;
}
</style>
