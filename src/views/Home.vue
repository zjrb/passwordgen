<template>
<div>
  <h1> Normal Password Generator </h1>
  <p>
    This will generate a simple password for you based on the lengtht that you specify! <br>
    <p>
    <input type="text" v-model="length" placeholder="Password Length"/>
    </p>
    <button @click="generatePassword">Generate</button>
    <p> {{password}} 
  </p>

</div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      password: "",
      length,
     };
  },
  methods:{
    generatePassword() {
      let result = "";
      const characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()";
     
      
      for(let i = 0; i < this.length; i++){
        result += characters[Math.floor(Math.random() * characters.length)];
      }
      this.password = result;
    }
  }
};
</script>
