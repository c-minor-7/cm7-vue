<template>
  <div id="app">
    <textarea
      class="cm7Src"
      :class="{ cm7Error: cm7Error }"
      v-model="src"></textarea>
    <Cm7
      class="cm7"
      :src="src"
      @error="cm7Error = $event" />
  </div>
</template>

<script>
import { readFileSync } from 'fs';
import Cm7 from '../../src/Cm7.vue';

const songs = {
  'here-we-are': readFileSync(__dirname + '/../cm7s/here-we-are.cm7', 'utf8'),
  'jimjim': readFileSync(__dirname + '/../cm7s/jimjim.cm7', 'utf8'),
};

export default {
  components: { Cm7 },
  data: () => ({
    cm7Error: false,
    songs,
    src: songs['here-we-are'],
  }),
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}

#app {
  display: flex;
  max-width: 1200px;
  flex-wrap: wrap;
  margin: 0 auto;
}

textarea {
  width: 50%;
}

.cm7 {
  width: 50%;
  padding: 1rem;
}

.cm7Src {
  white-space: pre;
  background: #daffe1;
  border: 1px solid #89ff86;
  font-family: monospace;
  padding: 1rem;
  resize: none;
  min-height: 100vh;
  width: 50%;
  font-size: inherit;
}

.cm7Error {
  border-color: #ff8686;
  background: #ffdada;
}
</style>
