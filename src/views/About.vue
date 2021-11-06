<template>
  <div class="about">
    <h1> Passphrase Generator </h1>
    <p>
      Generate a pass phrase using three words you specify and the number of characters 
      </p>
      <p>
    <input type="text" v-model="word1" placeholder="Word 1"/>
    </p>
    <p>
    <input type="text" v-model="word2" placeholder="Word 2"/>
    </p>
    <p>
    <input type="text" v-model="word3" placeholder="Word 3"/>
    </p>
    <p>
    <input type="text" v-model="chars" placeholder="Number of Characters"/>
    </p>
    <button @click="generate">Generate a Passphrase Using three words</button>
    <p> {{passphrase}}</p>
  </div>
</template>
<script>
export default {
  name: "About",
  data() {
    return {
      word1: "",
      word2: "",
      word3: "",
      chars: 0,
      passphrase: ""
     };
  },
  methods:
  {
    generate(){
      const characters = "abcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()_+";
      let passphrase = "";
      passphrase += this.word1;
      for(let i = 0; i <= this.chars; i++){
        passphrase += characters.charAt(Math.floor(Math.random() * characters.length));
      }
      passphrase += this.word2;
      for(let i = 0; i <= this.chars; i++){
        passphrase += characters.charAt(Math.floor(Math.random() * characters.length));
      }
      passphrase += this.word3;
      for(let i = 0; i <= this.chars; i++){
        passphrase += characters.charAt(Math.floor(Math.random() * characters.length));
      }
      this.passphrase = passphrase;
    }
        
  },
}

</script>
