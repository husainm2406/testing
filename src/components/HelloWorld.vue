<template>
  <div v-for="(user, i) in users" :key="i">
    <div>{{user.name}}</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      users: null,
    }
  },
  methods: {
    async getData() {
      const url = 'https://husainm2406.github.io/testing/db/db.json'
      let resp = await fetch(url);
      resp = await resp.json();
      console.log('resp',resp);
      this.users = resp;
      console.log(this.users);
    }
  },
  mounted(){
    this.getData();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
