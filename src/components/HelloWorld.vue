<template>
  <h1>{{ msg }}</h1>
  <img :src="image" alt="">
</template>
<script>
import axios from 'axios';

export default {
  props: {
    msg: {
      type: String
    }
  },
  data: () => ({
    image: null
  }),
  async mounted() {
    const res = await axios.get('http://localhost:5000/api/images');
    if (res.status === 200) {
      this.image = res.data.image;
    }
  }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
