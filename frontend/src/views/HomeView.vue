<template>
  <div class="home">000</div>
</template>

<script>
import { onMounted } from "vue";

export default {
  name: "HomeView",
  setup() {
    const GetTest = async () => {
      const response = await fetch("http://localhost:5000/api/test-get");
      const data = await response.json();

      console.log(data);
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
