<template>
  <div class="hello">
    <h1 :class="isActive ? 'active': ''" >{{ msg }}</h1>
    <button @click="handleAction">Click</button>
    <input v-model="message"/>
    <ul>
      <li v-for="(user, key) of userList" :key="key"> {{user}}</li>
    </ul>
    {{message}}
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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
    }
  }
}
</script>

<style>
.active{
  color: red;
}
</style>
