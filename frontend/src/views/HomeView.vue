<template>
  <div class="home">000</div>
</template>

<script>
import { onMounted } from "vue";

export default {
  name: "HomeView",
  setup() {
    const API_URL = process.env.VUE_APP_API_URL;
    
    const GetTest = async () => {
      fetch(`${API_URL}/api/test-get`)
        .then(response => response.json())
        .then(data => {
          console.log(data);
        })
        .catch(error => {
          console.error(error);
        });
    };

    onMounted(async () => {
      await GetTest();
    });

    return {
      GetTest,
    };
  },
};
</script>
