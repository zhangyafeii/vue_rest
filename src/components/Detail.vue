<template>
  <div>
    <h1>课程详细页面</h1>
    <div>
      <p>课程ID:{{detail.course}}</p>
      <p>课程图片：{{detail.img}}</p>
      <p>难度：{{detail.level}}</p>
      <p>口号：{{detail.course_slogan}}</p>
      <p>课程名字：{{detail.name}}</p>
      <p>为什么选择这门课程：{{detail.why}}</p>
      <div>
        <h3>课程章节</h3>
        <ul v-for="item in detail.chapters">
          <li>{{item.name}}</li>
        </ul>
      </div>

      <div>
        <h3>推荐课程</h3>
        <ul v-for="item in detail.recommends">
          <!-- <li><router-link :to="{name:'detail',params:{id:item.id}}">{{item.title}}</router-link></li> -->
          <li @click="changeDetial(item.id)"><a href="javasript:">{{item.title}}</a></li>
        </ul>
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    name: "index",
    data() {
      return {
        detail:{
          course:null,
          img:null,
          level:null,
          slogon:null,
          title:null,
          why:null,
          chapter:[],
          recommends:[],
        }
      }
    },
    mounted(){
      var id = this.$route.params.id
      this.initDetail(id)
    },
    methods:{
      initDetail(nid){
        var that = this
        this.$axios.request({
          url:this.$store.state.apiList.courseDetail + nid +'/',
          method:'GET'
        }).then(function (arg) {
          if(arg.data.code === 1000){
            that.detail = arg.data.data
          }else{
            alert(arg.data.error)
          }
        })
      },
      changeDetial(id){
        this.initDetail(id)
        this.$router.push({name:'detail',params:{id:id}})
      }
    }
  }
</script>

<style scoped>

</style>
