<script setup></script>

<template>
  <div class="entireAccordion">
    <button
      @click="toggleAccordion()"
      class="button"
      :aria-expanded="isOpen"
      :aria-controls="`collapse${_uid}`"
    >
      <slot name="title" />
      <img
        src="../assets/pics/upArrow.png"
        alt="error"
        v-bind:style="{ transform: `rotate(${deg}deg)` }"
      />
    </button>

    <div v-show="isOpen" :id="`collapse${_uid}`">
      <slot name="content" />
    </div>
  </div>
</template>

<style scoped>
.entireAccordion {
  width: 250px;
  margin-bottom: 10px;
}

.button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  background: none;
  border: 2px solid black;
  width: 250px;
  transition-duration: 0.3s;
  background-color: #83c5a7;
  position: relative;
}

.button:hover {
  background-color: #7c3a58;
  color: azure;
  cursor: pointer;
}

img {
  width: 25px;
  height: 30px;
  transform: rotate(180deg);
}
</style>

<script>
export default {
  data() {
    return {
      isOpen: false,
      isActive: false,
      marginBottom: 100,
    };
  },

  methods: {
    toggleAccordion() {
      this.isOpen = !this.isOpen;
      this.deg += 180;
    },
  },
};
</script>
