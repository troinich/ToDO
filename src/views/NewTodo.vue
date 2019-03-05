<template>
    <main id = "new-todo">
        <header>
        </header>
        <section class="content">
            <input type="text" v-model="newTodo">
        </section>
        <footer>
            <p>{{newTodo.length}} / 30 tecken</p>
            <a href="#" class="btn" @click="addTodo">Add new Todo</a>
        </footer>
    </main>
</template>
<script>
export default {
    name: 'newTodo',
    data(){
        return{
            newTodo:""
        }
    },

methods:{
    addTodo(){
        let todo={
            done:false,
            text:this.newTodo  
        }
        this.$emit('newtodo', todo);
        this.newTodo='';
        this.$emit('swipe', 0)
    }
}
}
</script>
<style lang="scss">
#new-todo{
    display:flex;
    flex-direction: column;
    header{
        flex:3;
        //@extend %center;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .content{
        display: flex;
        justify-content: center;
        align-items: center;
        flex:10;

        input{
            font-size: 1.4rem;
            font-weight: 700;
            border: 1px black solid;
            appearance: none;
            background: none;
            text-align: center;
            padding: .25rem;
              &:focus {
                    outline: none;
              }
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
            font-weight: 700;
            border-radius: 99rem;
        }
    }
}
</style>
