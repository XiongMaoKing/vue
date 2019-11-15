<template>
  <div>
      <div is='vmain'></div>
      <div is='vfooter' :fl='fl'></div>
  </div>
</template>

<script>
import vmain from '@/components/main'
import vfooter from '@/components/footer'
export default {
    components:{vmain,vfooter},
    data(){
      return{
        fl:''
      }
    },
    beforeRouteUpdate(to,from,next){
      let path=to.params.path;
      this.fl=this.$store.state.data[path].friendLink;
      next();
    }
}
</script>

<style>

</style>