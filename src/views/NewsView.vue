<template>
  <section>
    <div v-for="(item, index) in users" :key="index">
      {{ user }}
    </div>
  </section>
</template>

<script>
import { fetchNewsList } from "../api";

export default {
  data() {
    return {
      users: [],
    };
  },
  created() {
    fetchNewsList
      .then(res => (this.users = res.data))
      .catch(err => console.log(err));
  },
};
</script>

<style></style>
