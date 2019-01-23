<template>
  <div>
    <h2>LuffyX学位:{{title}}</h2>
  </div>
</template>

<script>
  export default {
    name: "index",
    data() {
      return {
        title:null
      }
    },
    mounted(){
      // if (!this.$store.state.token) {
      //   this.$router.push({name:'login'})
      // }
      this.initMicro()
    },
    methods:{
      initMicro(){
        var that = this
        this.$axios.request({
          // url:'http://127.0.0.1:8000/api/v1/micro/',
          url:this.$store.state.apiList.micro,
          method:'GET',
          params:{
            token:this.$store.state.token
          }
        }).then(function(arg){
          if (arg.data.code == 1000) {
            console.log(arg.data)
            that.title = arg.data.data
          }
        })
      }
    }
  }
</script>

<style scoped>

</style>
