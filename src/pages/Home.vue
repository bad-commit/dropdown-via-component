<template>
  <div class="dropdown">
    <button class="button" @click.stop="showMenu()">Toggle</button>
    <div class="menu" :style="{ display: active ? 'block' : 'none' }">
      <ul @click.stop>
        <li>a</li>
        <li>b</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false,
    };
  },
  methods: {
    showMenu() {
      this.active = !this.active;
    },
    close() {
      this.active = false;
    },
  },
  mounted() {
    document.addEventListener("click", this.close);
  },
  unmounted() {
    document.removeEventListener("click", this.close);
  },
};
</script>
