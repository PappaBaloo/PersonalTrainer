<script setup>
import TheAccordionVue from "./components/TheAccordion.vue";
</script>

<template>
  <header class="all">
    <nav class="navbar">
      <h1 class="name_logo">Personal Trainer Finder</h1>
      <button class="upload" type="button">Upload Profile</button>
    </nav>
    <div class="search_filter_profiles">
      <div class="search_filters">
        <form action="" method="get" class="form">
          <input class="searchBar" type="search" placeholder="Search..." />
          <button type="submit" class="search-button">
            <img src="./assets/pics/search.png" alt="error" />
          </button>
        </form>
        <the-accordion-vue class="accordion">
          <template v-slot:title>
            <span>Filters</span>
          </template>
          <template v-slot:content>
            <p>tjena</p>
          </template>
        </the-accordion-vue>
      </div>
      <div class="profiles"></div>
    </div>
  </header>
</template>

<script>
export default {
  name: "App",
  components: {
    TheAccordionVue,
  },
};
</script>

<style scoped>
.all {
  display: grid;
  grid-template-rows: 0.4fr 1.6fr;
  width: 100%;
  height: 100%;
  margin: 0%;
}

.navbar {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  border-bottom: 2px solid gray;
}

.name_logo {
  float: left;
}

.upload {
  height: 50px;
  width: 100px;
  margin-left: auto;
  margin-top: 6px;
  padding: 1%;
  background-color: #3662ae;
  color: azure;
  border: 1px solid black;
  border-radius: 8px;
  transition-duration: 0.4s;
}

.upload:hover {
  background-color: #14233c;
}

.search_filter_profiles {
  display: grid;
  place-items: center;
  grid-template-columns: 0.6fr 1.4fr;
  grid-template-rows: 1fr;
  grid-column: 1;
  grid-row: 2;
  margin: 2%;
}

.search_filters {
  grid-column: 1;
  display: inline-flex;
  flex-direction: column;
  margin: 1%;
}

.form {
  display: flex;
  flex-direction: row;
}

.searchBar {
  border: 2px solid black;
  padding: 2%;
  border-radius: 100px;
  width: 100%;
}

.search-button {
  background: transparent;
  border: none;
  outline: none;
  margin-left: -33px;
}
.search-button img {
  width: 20px;
  height: 20px;
  object-fit: cover;
}

.search-button img:hover {
  cursor: pointer;
}

.accordion {
  margin-top: 20px;
}

.profiles {
  grid-column: 2;
}
</style>
