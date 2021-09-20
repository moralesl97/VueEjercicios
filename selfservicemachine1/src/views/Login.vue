<template>
  <div>
    <h1>Login</h1>
    Name:<input type="text" v-model="name">
    Password:<input type="password" v-model="password"> 
    <button style="margin-left: 1em;" @click="logIn()">Login</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            password: '',
        }
    },
    methods:{
        logIn: function(){
            if(this.name == '' || this.password == ''){
                alert('Introduce name and password');
            }else{
                this.$router.push({
                    name: 'Home',
                    params: {data: true, name: this.name, pass: this.password}
                });
            }   
        }
    }
}
</script>

<style>

</style>