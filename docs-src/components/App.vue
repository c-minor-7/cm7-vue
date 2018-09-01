<template>
  <div id="app">
    <textarea
      class="cm7Src"
      :class="{ cm7Error: cm7Error }"
      v-model="src"></textarea>
    <Cm7
      class="cm7Container"
      :src="src"
      @error="cm7Error = $event" />
  </div>
</template>

<script>
import Cm7 from '../../src/Cm7.vue';

export default {
  components: { Cm7 },
  data: () => ({
    cm7Error: false,
    src: `key = D

:: intro ::
1 4
-
1 4
-

:: verse ::
1 4
() Here we are in the (future) now
1 4 2m
() Here we are in the (place) that we wanted to (be)
7b
To (be)

1 4
() Everything in your (fantasy)
1 4 2m
() Everything has be(come) your reali(ty)
7b
(Hmmm)

:: pre-chorus ::
4 5
() What a fool I (used) to be
4 5
() Should have known you mean the (most) to me
4   4
() Now I finally (see) it
2m
Now I finally (know) it
-
All I really want
2m
() All I really want is


:: chorus ::
1
(I) just wanna be with you
1
(I) just wanna be with you
       4
Right (now)
1
(I) just wanna be with you
1
(I) just wanna be with you
4
Right (now)
2
I (didn't) know
2m
It (runs) so fast
2m7b5
And I (can't) catch up`
  }),
};
</script>

<style scoped>
#app {
  display: flex;
  max-width: 1200px;
  flex-wrap: wrap;
  margin: 0 auto;
}

textarea {
  width: 50%;
}

.cm7Container {
  width: 50%;
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
