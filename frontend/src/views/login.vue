<template>
  <div class="loginblock">
    <div class="uppart">
      <span></span>
      <span></span>
    </div>
    <div class="downpart">
      <span></span>
      <span></span>
    </div>
    <div>
      <form>
        <label>用户名</label>
        <input type='text' required v-model="username"/><br/>
        <label>密码</label>
        <input type='password' required v-model="password"/><br/>
        <input type="submit" @click="updataall"/>
      </form>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useStore } from 'vuex'

export default defineComponent({
  name: 'login',
  components: {
  },
  data () {
    return {
      username:'',
      password:'',
      store: useStore(),
    }
  },
  methods: {
    updataall(){
      console.log(this.username);
      
      if(this.username!=''&& this.password!=''){
        this.store.commit('saveusername',this.username);
        this.$router.push('/model_info_manage')
      }
    }
  },
});
</script>

<style scoped>
.loginblock{
  display: block;
}
</style>


