<template>
    <div id="login">
        <h1>我是第一个项目测试</h1>
        <div v-for="user in users"
                :key="user.id">{{user.username}}
        </div>
    </div>
</template>

<script>
export default {
    name: 'login',
    data() {
        return{
            users: []
        }
    },
    created(){
    //   this.$http.get("https://jsonplaceholder.typicode.com/posts")
    this.$http.post('/api/login')
      .then(function(data){
        this.users = data.body
        console.log(this.users)
      })
  },
}

</script>

<style>

</style>
