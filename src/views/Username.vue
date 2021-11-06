<template>
  <div class="Username">
    <h1> Usernname Generator </h1>
    <p>
      Generate a username based on your name.
      </p>
      <p>
    <input type="text" v-model="first" placeholder="First Name"/>
    </p>
    <p>
    <input type="text" v-model="last" placeholder="Last Name"/>
    </p>
    <button @click="generate">Generate Username</button>
    <p> {{username}}</p>
  </div>
</template>
<script>
export default {
  name: "Username",
  data() {
    return {
      first: "",
      last: "",
      username: "",
     };
  },
  methods:
  {
    generate(){
        const characters = "abcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()";
      let num = Math.floor(Math.random() * 5);
      if(num === 1)
      {
        this.username = this.first + this.last;
      }
      else if(num === 2)
      {
        this.username = this.last + this.first;
      }
      else if(num === 3)
      {
        this.username = this.first + this.last.charAt(0);
      }
      else if(num === 4)
      {
        this.username = this.last + this.first.charAt(0);
      }
      for(let i = 0; i <= num; i++)
      {
        let random = Math.floor(Math.random() * characters.length);
        this.username += characters.charAt(random);
      }
    }
        
  },
}

</script>
