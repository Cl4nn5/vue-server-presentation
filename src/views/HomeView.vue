<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
    <section>
      <!-- <input type="text" v-model="soundMsg" /> -->
      <button @click="soundThx(soundMsg)">감사합니다</button>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src

export default defineComponent({
  name: "HomeView",
  components: {
    HelloWorld,
  },
  data() {
    return {
      soundMsg: "감사합니다",
    };
  },
  methods: {
    soundThx(msg = "감사합니다") {
      const s = new SpeechSynthesisUtterance(msg);
      s.lang = "ko-KR";
      s.rate = 1;
      s.pitch = 1;
      s.voice = speechSynthesis.getVoices()[12];
      window.speechSynthesis.speak(s);
    },
  },
});
</script>
