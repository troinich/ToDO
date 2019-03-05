<template>
  <div id="app">
    <section class="slider" :class="'slide-'+ activeSlide">
      <todos :vv="todos" @swipe="handleSwipe"/>
   
      <newtodo @swipe="handleSwipe" @newtodo="newTodo"/>
    </section>
  </div>
</template>

<script>
import todos from "./views/Todos.vue";
import newtodo from "./views/NewTodo.vue";

export default {
  name: "app",
  data(){
    return{
      todos:[
        {done:false, text:'Kop bananer'},
        {done:false, text:'Ketchup'},
        {done:true, text:'Applen'}
      ],
      activeSlide:0
    }
  },
  components: {
    todos,
    newtodo
  },
  methods:{
    handleSwipe(e){
      console.log('swipe');
      this.activeSlide = e;
    },
    newTodo(todo){
      this.todos.push(todo);
    }
  }
};
</script>

<style lang="scss">
@import "scss/main.scss";

.slider {
  width: 200vw;
  display: flex;
  height: inherit;
}

main {
  flex: 1;
}
</style>
