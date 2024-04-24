<template>
  <header>
    <h1 class="text-center">Workshop</h1>
  </header>
  <main>
    <ColorsList />
  </main>
</template>

<script>
import { store } from './store.js';
import ColorsList from './components/ColorsList.vue';

export default {
  name: 'App',
  components: {
    ColorsList

  },
  data() {
    return {
      store
    }
  }
}
</script>

<style lang="scss" scoped></style>