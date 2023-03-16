<script setup>
  import Userform from "@/components/Userform.vue"

function Login(user){
  // api request
}

</script>

<template>
    <div>
      <Userform formType = "signin" @submit="login" />
      <!-- Login page -->
    </div>
</template>
  