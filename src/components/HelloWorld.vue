<template>
  <h3>
    {{ msg }}
  </h3>
  <br />
  <div class="hello">
    <OptionApi />
    <CompositionApi />
    <SetupScript />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import OptionApi from "@/components/compare/OptionApi.vue";
import CompositionApi from "@/components/compare/CompositionApi.vue";
import SetupScript from "@/components/compare/SetupScript.vue";

export default defineComponent({
  name: "HelloWorld",
  components: {
    OptionApi,
    CompositionApi,
    SetupScript,
  },
  props: {
    msg: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
