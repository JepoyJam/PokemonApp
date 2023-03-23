<template>
    <div>
        <!-- Sign up page -->
       <Userform formType = "signup" @submit="Register" />
    </div>
</template>

<script setup>
 import Userform from "@/components/Userform.vue"
 import client from "@/assets/apiclient.js"
//  import {ref, onMounted} from "vue"
 import axios from "axios"



function Register(user){
  axios.post(client, user)
  .then(res => {
  console.log("res data", res)
  })
  .catch(errors =>{
      console.log("error", errors)
 })
  }



 
//  .then(Register => this.RegisterData, Register.data)
//  .catch(errors => {console.log("error", errors)})

// const register = ref("Register")

//   onMounted(()=>{
//       client.post("/signup").then(register => {
//       console.log("user respond", register)
      
//     })
//     .catch(errors =>{
//       console.log("error", errors)
//     })
//   })



  // function register() {
  //   fetch("http://127.0.0.1:8000/signup", {
  //     method: "POST",
  //     body: JSON.stringify(Register),
  //     headers: "Authorization"
  //   })
  // }


// onMounted(()=>{
//     client.post("/signup").then(res => {
//         console.log("data sent", res.data)
//         userdata = res.data
//     }).catch(errors=>{
//         console.log("error", errors)
//     })
// })

// onMounted(()=>{
//     client.post('/signup')  
//     .then((user)=>{
//       console.log("response received", user.data)
//       userDetails.value = user.data
//     }).catch(errors=>{
//         console.log("error", errors)
//     })
//   // api new data
// })
    


// function Register(user){
//   fetch("http://127.0.0.1:8000/signup", {
//     method: "POST",
//     body: JSON.stringify(user),
//     headers: {
//       "Content-Type": "application/json",
//     } 
//   })
//   .catch(errors=>{
//         console.log("error", errors)
//     })
// }
 // HomeView.vue
</script>

