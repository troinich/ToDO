<template>
<article class="todo" :class="{completed: todo.done }" v-touch:swipe.right="completed">
    <aside class="done" v-if="todo.done">
        <img src='../assets/Vector.svg'>
    </aside>
        <section class="text">
            {{todo.text}}
        </section>
</article>
</template>
<script>
export default {
    name:'todo',
    props: ['todo', 'index'],
    data(){
        return{
        }
    
    },
    methods:{
        completed(){
            console.log(this.index);
            this.$parent.$parent.todos[this.index].done=!this.$parent.$parent.todos[this.index].done;
        }
    }
}
</script>

<style lang="scss">
.todo{

    background: rgba($color: #000000, $alpha: .1);
    padding: .25rem;
    height: 3rem;
    display: flex;
    border-radius: 999rem;
    margin: 0 0 1rem;

    &.completed{
    
        .text{
            color: rgba($color: #000000, $alpha: .5);
            text-decoration: line-through;
        }
    }

    aside{
        background: rgb(56, 180, 128);
        width: 3rem;
        height: 3rem;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 999rem;
    }
    .text{
        flex:1;
        display:flex;
        align-items: center;
        padding: 0 0 0 1rem;
    }

}
</style>
