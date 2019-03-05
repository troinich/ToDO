<template>
    <main id = "todos">
        <header>
            <h1>TEFLON</h1>
            <p>hjälp när det inte fastnar</p>
        </header>
        <section class="content">
       <todo v-for="(todoData, index) in todos" :key="index" :todo="todoData" :index="index">
       </todo>
        </section>
        <footer>
            <a href="#" class="btn" v-touch:swipe.left="swipe">Slide to add new</a>
        </footer>
    </main>
</template>
<script>
import todo from '../components/Todo'
export default {
    name: 'todos',
    methods:{
        swipe(){
            this.$store.commit('swipe', 1);
        }
    },
    components:{
        todo
    },
    computed:{
    todos(){
       /*  let todos = this.$store.getters.todos
        return todos.filter(todo=> todo.done == true) */
        return this.$store.getters.todos;

    }
}
}
</script>
<style lang="scss">
#todos{

    header{

        h1{
            margin:0;
            padding:0;
            font-weight: 700;
        }
        p{
            margin:0;
            font-style: italic;
        }
    }

     footer{
        display: flex;
        flex-direction: column;
        justify-content: flex-end;

        a.btn{
            display: flex;
            justify-content: center;
            align-items: center;
            background: #222;
            color:white;
            text-decoration: none;
            height: 4rem;
            border-radius: 99rem;
        }
    }
}
</style>
