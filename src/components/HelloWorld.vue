<template>
  <div class="hello">
    <!-- <h1 :class="isActive ? 'active': ''" >{{ msg }}</h1> -->
    <h1 :class="{ active: isActive }" >{{ msg }}</h1>
    
    <button @click="handleAction">Click</button>
    <input v-model="message"/>
    <ul>
      <li v-for="(user, key) of userList" :key="key"> {{user}}</li>
    </ul>
    {{message}}
  </div>
  <ChildInjector @messageFromChild="childMessageData"/>
</template>

<script>

import ChildInjector from './ChildInjector.vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  components: {
    ChildInjector
  },
  
  data(){
    return{
      isActive: false,
      message: '',
      userList : ['Ali', 'Usman']
    }
  },
  methods:{
    handleAction(){
      this.isActive = !this.isActive
    },
    childMessageData(arg1) {
      console.log('event from child, child data', arg1)
    }
  }
}
</script>

<style>
.active{
  color: red;
}
</style>
