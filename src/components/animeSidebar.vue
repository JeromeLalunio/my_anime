<template>
  <div class="sidebar">
    <anime-tile
      v-for="anime in animeList"
      :key="anime.name"
      :name="anime.name"
      :episodes="anime.episodes"
    ></anime-tile>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import animeTile from "./animeTile.vue";

export default defineComponent({
  name: "animeSidebar",
  components: {
    animeTile,
  },
  props: {
    animeList: Array,
  },
});
</script>

<style lang="scss" scoped>
@import "../styles/variables.scss";
@import "../styles/mixins.scss";
@import "../styles/extension.scss";

.sidebar {
  background: $primaryLight;

  @extend .rounded-border;
  @include shadow;

  @include desktop {
    width: 20vw;
    height: 100vh;
  }

  @include mobile {
    width: 95vw;
    margin: 0.2em auto;
  }
}
</style>