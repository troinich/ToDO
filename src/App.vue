<template>
  <div id="app">
    <section class="slider" :class="'slide-'+ activeSlide">
      <todos />
   
      <newtodo />
    </section>
  </div>
</template>

<script>
import todos from "./views/Todos.vue";
import newtodo from "./views/NewTodo.vue";

export default {
  name: "app",
 
  components: {
    todos,
    newtodo
  },
 
  computed:{
    activeSlide(){
      return this.$store.state.activeSlide;
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
