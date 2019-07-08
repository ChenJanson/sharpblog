<template>
  <div class="ping">
    <button type="button" class="btn btn-primary">{{ msg }}</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'ping',
  data () {
    return {
      msg: ''
    }
  },
  methods:{
    getMessage(){
      const path = 'http://localhost:5000/api/ping'
      axios.get(path)
          .then((res)=>{
            this.msg = res.data
          })
          .catch((error)=>{
            console.log(error)
          })
    }
  },
  created(){
    this.getMessage()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
