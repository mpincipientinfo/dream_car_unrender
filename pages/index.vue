<template>
  <div>
    <Home />
  </div>
</template>

<script>
import params from "@/config/params.js";
import Home from "@/components/home";
export default {
  components: {
    Home
  },
  head() {
    return {
      title: params.title
    };
  }
};
</script>
