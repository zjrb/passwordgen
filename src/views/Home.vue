<template>
  <h1>Hello World {{message}}</h1>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      message: "Hello World"
    };
  }
};
</script>
