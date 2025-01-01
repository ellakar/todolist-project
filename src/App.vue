<template>
  <h1> {{ title }}</h1>
  <div> 
  <button @click = "clickevent"> Add an item</button>
  <input type ="text" v-model="list" placeholder="Enter items..." @keyup.enter="clickevent"/>
  <ul>
    <li v-for ="(input,index) in inputs" :key="index" >
      {{ input }}
      <button @click ="deleteItem">Delete</button>
    </li>
  </ul>
  </div>
</template>


<script> 
export default{
data(){
  return{
    title: "The Famous ToDoList",
    list: '',
   inputs:[]
  }
},
 methods:{
  clickevent(){
    this.inputs.push(this.list )
    this.list=''
  },
  deleteItem(){
    this.inputs.pop(this.list)
  }
 }
}
</script>


<style>
input {
  padding: 10px;
  margin-right: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 8px 15px;
  background-color: #df37c5;
  color: rgb(10, 7, 7);
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #9f72e7;
}

ul {
  margin-top: 20px;
  list-style-type: none;
  padding: 0;
}

li {
  padding: 5px 0;
  font-size: 18px;
}
h1{
  padding: 10px;
  margin-right: 102px;
  font-size: 50px;
  color: #928f9b;

}
</style>