<template>
  <div> Man o man message = {{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted(){
    const { text } = await (await fetch("/api/message")).json();
    this.message = text;
  }
};
</script>
