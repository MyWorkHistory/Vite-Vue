<template>
    <div>
        <p>{{ name }}</p>
        <input ref="el" type="text" placeholder="Input Name" v-model="name" />
        <div>
            <button @click="submitForm" v-bind:disabled="name.length == 0">Submit</button>
        </div>
    </div>
</template>

<script>
import {ref,onMounted} from 'vue'
export default{
    setup(){
        const name = ref('')
        const submitForm = () => {
            console.log(`For Submitted: Name = ${name.value}`)
        }
        const el = ref()
       
        onMounted(()=>{
            el.value.focus()
        })
        return{
            el,
            name,
            submitForm,
        }
    }
}
</script>

<style>
input[type = 'text']{
    padding: 5px;
}

button{
    margin-top: 20px;
}
</style>