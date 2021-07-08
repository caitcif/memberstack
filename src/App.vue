<template>
  <Memberstack />
  <router-view />
</template>
<script>
import { defineComponent } from "vue";
import Memberstack from "components/Memberstack";

export default defineComponent({
  name: "App",
  components: { Memberstack },
});
</script>
