<template>
    <form class="flex flex-col mt-10 space-y-7" @submit.prevent="submitForm">
        <div v-if="formType == 'signup'" class="form-group">
            <label for="" class="label">Full name</label>
            <input type="text" name="fullname" v-model="user.fullname" class="input"/>
        </div>
        <div v-if="formType == 'signup'" class="form-group">
            <label for="" class="label">Gender: </label>
            <select v-model="user.gender" class="input">
                <option value="Male">Male</option>
                <option value="Female">Female</option>
            </select>
        </div>  
        <div class="form-group">
            <label for="" class="label">Email</label>
            <input type="email" name="email" v-model="user.email" class="input"/>
        </div>  
        <div class="form-group">
            <label for="" class="label">Password</label>
            <input type="password" name="password" v-model="user.password" minlength="8" class="input"/>
        </div>
         <div v-if="formType == 'signup'" class="checkbox">
            <input type="checkbox" v-model="user.terms" required class="label"/>
            <label class="input">Terms and Conditions</label>
        </div>
        <button class="button">{{ formType == "signup" ? 'Sign Up' : 'Sign In' }}</button>
    </form>


</template>

<script setup>
import { reactive } from "vue"

defineProps({
    formType: {
        type: String,
        default: "signup"
    }
})

const emit = defineEmits(["submit"])
function submitForm(){
    emit("submit", user)
}

const user = reactive ({
    fullname: "", 
    gender: "",
    email: "",
    password: "",   
    terms: false,       
})

</script>

<style scoped>
.input {
    @apply border border-gray-200 p-2 rounded-md w-full;
}
.label {
    @apply text-lg text-gray-700 font-semibold;
}
.button{
    @apply bg-purple-500 text-gray-50 px-4 py-2 rounded;
}
.form-group {
    @apply flex flex-col space-y-1;
}
.checkbox {
    @apply text-lg text-gray-700 font-semibold static space-x-4;
}

</style>