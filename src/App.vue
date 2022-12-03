<template>
  <h1 class="text-center mb-0">My Daily Routine </h1>
  <div class="container">
    <div class="row d-flex justify-content-center" >
      <div class="col-6 ">
        <div v-show="incompleteList.length"  >
          <h3 class=" mt-5" >List In Progress</h3>
        <ul class="  text-black-50 w-auto ">
          <li v-for="plist in incompleteList" :key="plist.id">
            <label for="">
              {{plist.name}}
              <input type="checkbox" v-model="plist.complete">
            </label></li>
        </ul>
        </div>
       <div  v-show=" completedList.length" >
        <h3 class=" mt-5">Completed List</h3>

        <ul class="   text-black-50 w-auto ">
          <li v-for="plist in completedList " :key="plist.id" >
            <label for="">

              {{plist.name}}
              <input type="checkbox" v-model="plist.complete">
            </label></li>
        </ul>
              </div>
              
              </div>
            </div>
            
          </div>
</template>

<script>
  export default {
    data() {
      return {
        plists:[
          {name:"Listen Songs",complete:false,id:1},
          {name:"Drink Coffee",complete:false,id:2},
          {name:"coding",complete:false,id:3}
        ]
      }
    },
    computed: {
      completedList() {
        return this.plists.filter(c=>c.complete)
      },
      incompleteList(){
        return this. plists.filter(c=> !c.complete)
      }
    },
    
  }
</script>

<style>
@import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
@import "../node_modules/bootstrap-icons/font/bootstrap-icons.css"

</style>