<template>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.9.1/font/bootstrap-icons.css">  
  <div class=" mt-5">
        <h2 class="fw-bold">Todo App</h2>
        <form class="mt-4 mx-auto" @submit.prevent="addTodo">
            <label class="d-flex text-start mb-2">New Todo</label>
            <input type="text" class="mb-3" v-model="todo">
            <div  v-if="error"><p class="error">{{error}}</p></div>
            <button class="fw-bold fs-sm-6 fs-md-5 mt-2 mb-3" @keypress.enter.prevent="addTodo">Add Todo</button>
            <h3 class="d-flex text-start fw-bold mt-3 fs-6 fs-md-5">Todo List</h3>
            <hr>
                <div v-for="todo in todos" :key="todo" class="d-flex justify-content-between align-items-center ">
                <div>
                    <p class="" v-if="todo">{{todo}}</p>
                </div>
                <div class="me-sm-4"><i class="bi bi-trash-fill fs-5" @click="deleteTodo(todo)"></i></div>
                </div>
            
        </form>
    </div>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
    setup(){
        let todo=ref("");
        let todos=ref([]);
        let error=ref("");
        let addTodo=()=>{
            if(todo.value){
                todos.value.push(todo.value);
                todo.value="";
            }else{
                error.value="You need to fill this field!";
            }
        }
        let deleteTodo=(todo)=>{
            todos.value=todos.value.filter((t)=>{
                return t!=todo;
            })
        }
        return {todo,addTodo,todos,deleteTodo,error};
    }
}
</script>

<style>
    @media screen and (max-width:1399.98px) {
        form{
        width: 600px;
        }

        label{
            color: #fff;
            font-size: 15px;
            font-weight: bold;
        }
        input{
            width: 100%;
            height: 60px;
            border: 2px solid gray;
            border-radius: 10px;
            background: #000;
            color: #fff;
            padding:5px 15px;
        }

        form button{
            width: 100%;
            height: 50px;
            color: #000;
            background-color: gray;
            border: 1px solid gray;
            border-radius: 10px;
        }
    
        p{
            width: 100%;
            height: 60px;
            background: #000;
            color: #fff;
            padding:15px;
        }
        
        i:hover{
            cursor: pointer;
        }

        .error{
            color: crimson;
        }
    }

    @media screen and (max-width:1199.98px){
        form{
            width: 550px;
        }

        label{
            color: #fff;
            font-size: 12px;
            font-weight: bold;
        }

        input{
            width: 100%;
            height: 40px;
            border: 1px solid gray;
            border-radius: 10px;
            background: #000;
            color: #fff;
            padding:5px 10px;
        }

        button{
            width: 100%;
            height: 40px;
            color: #000;
            background-color: gray;
            border: 1px solid gray;
            border-radius: 10px;
        }

        p{
            width: 100%;
            height: 40px;
            background: #000;
            color: #fff;
            padding:12px;
        }

        i:hover{
            cursor: pointer;
        }

        .error{
            color: crimson;
        }
    }

    @media screen and (max-width:991.98px){
        form{
            width: 500px;
        }

        label{
            color: #fff;
            font-size: 12px;
            font-weight: bold;
        }

        input{
            width: 100%;
            height: 40px;
            border: 1px solid gray;
            border-radius: 10px;
            background: #000;
            color: #fff;
            padding:5px 10px;
        }

        button{
            width: 100%;
            height: 40px;
            color: #000;
            background-color: gray;
            border: 1px solid gray;
            border-radius: 10px;
        }

        p{
            width: 100%;
            height: 40px;
            background: #000;
            color: #fff;
            padding:12px;
        }

        i:hover{
            cursor: pointer;
        }

        .error{
            color: crimson;
        }
    }
    @media screen and (max-width:767.98px){
        form{
        width: 450px;
        }

        label{
            color: #fff;
            font-size: 12px;
            font-weight: bold;
        }

        input{
            width: 100%;
            height: 40px;
            border: 1px solid gray;
            border-radius: 10px;
            background: #000;
            color: #fff;
            padding:5px 10px;
        }

        button{
            width: 100%;
            height: 40px;
            color: #000;
            background-color: gray;
            border: 1px solid gray;
            border-radius: 10px;
        }

        p{
            width: 100%;
            height: 40px;
            background: #000;
            color: #fff;
            padding:13px;
        }

        i:hover{
            cursor: pointer;
        }

        .error{
            color: crimson;
        }
    }

    @media screen and (max-width:575.98px){
        form{
            width: 300px;
        }

        label{
            color: #fff;
            font-size: 12px;
            font-weight: bold;
        }

        input{
            width: 100%;
            height: 40px;
            border: 1px solid gray;
            border-radius: 10px;
            background: #000;
            color: #fff;
            padding:5px 10px;
        }

        button{
            width: 100%;
            height: 40px;
            color: #000;
            background-color: gray;
            border: 1px solid gray;
            border-radius: 10px;
        }

        p{
            width: 100%;
            height: 40px;
            background: #000;
            color: #fff;
            padding:12px;
        }

        i:hover{
            cursor: pointer;
        }

        .error{
            color: crimson;
        }
    }
</style>