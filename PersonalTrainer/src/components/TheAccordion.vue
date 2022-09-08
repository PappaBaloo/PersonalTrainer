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
        @click="toggleImgRotate"
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
  height: 100px;
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
}

.button:hover {
  background-color: gray;
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
