<template>
    <div id='app'>
    <input type='button' value='登录' @click='flag=!flag'>
        <div is='login' v-if='flag'></div>
        <div is='vheader'></div>
        <router-view />
        </div>
</template>

<script>
import vheader from '@/components/header'
import login from '@/components/login'
export default {
    name:'App',
    created(){
        this.axios.get('static/data.json').then((data)=>{
            this.$store.dispatch('saveData',data.data)
        })
    },
    components:{vheader,login},
    data(){
        return{
            flag:false
        }
    }
}
</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
