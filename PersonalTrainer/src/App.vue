<script setup>
import TheAccordionVue from "./components/TheAccordion.vue";
import TheProfileVue from "./components/TheProfile.vue";
</script>

<template>
  <header class="all">
    <nav class="navbar">
      <h1 class="name_logo">Personal Trainer Finder</h1>
      <div class="uploadDiv">
        <button class="upload" type="button">Upload Profile</button>
      </div>
    </nav>
    <div class="search_filter_profiles">
      <div class="search_filters">
        <form action="" method="get" class="form">
          <input class="searchBar" type="search" placeholder="Search..." />
          <button type="submit" class="search-button">
            <img src="./assets/pics/search.png" alt="error" />
          </button>
        </form>
        <div class="accordionGroup">
          <the-accordion-vue class="accordion">
            <template v-slot:title>
              <span>Mål av träning</span>
            </template>
            <template v-slot:content>
              <fieldset class="fieldGoal">
                <ul>
                  <li class="listClass">
                    <label for=""><input type="checkbox" /></label>
                    <span>Förlora fett</span>
                  </li>
                  <li class="listClass">
                    <label for=""><input type="checkbox" /></label>
                    <span>Öka muskelmassa</span>
                  </li>
                  <li class="listClass">
                    <label for=""><input type="checkbox" /></label>
                    <span>Bättre kondition</span>
                  </li>
                  <li class="listClass">
                    <label for=""><input type="checkbox" /></label>
                    <span>Bättre boxning</span>
                  </li>
                </ul>
              </fieldset>
            </template>
          </the-accordion-vue>

          <the-accordion-vue>
            <template v-slot:title>
              <span>Ålder</span>
            </template>
            <template v-slot:content>
              <fieldset>
                <div class="agewrapper">
                  <header>
                    <span>Använd slider eller skriv in min och max ålder</span>
                  </header>
                  <div class="ålderInput">
                    <div class="field">
                      <span>Min</span>
                      <input type="number" class="inputMin" value="18" />
                    </div>
                    <div class="seperator">-</div>
                    <div class="field">
                      <span>Max</span>
                      <input type="number" class="inputMax" value="80" />
                    </div>
                    <div class="slider">
                      <div class="progress"></div>
                    </div>
                    <div class="range-input">
                      <input
                        type="range"
                        class="range-min"
                        min="18"
                        max="80"
                        value="18"
                      />
                    </div>
                    <div class="range-input">
                      <input
                        type="range"
                        class="range-max"
                        min="18"
                        max="80"
                        value="80"
                      />
                    </div>
                  </div>
                </div>
              </fieldset>
            </template>
          </the-accordion-vue>
        </div>
      </div>
      <div class="profiles">
        <TheProfileVue></TheProfileVue>
      </div>
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
  padding: 5px;
  padding: 1%;
  background-color: #83c5a7;
  color: black;
  border: 1px solid black;
  border-radius: 8px;
  transition-duration: 0.4s;
  text-align: center;
}

.uploadDiv {
  margin-left: auto;
  margin-top: 6px;
}

.upload:hover {
  background-color: #7c3a58;
  color: azure;
  cursor: pointer;
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
.accordionGroup {
  display: block;
}

.listClass {
  list-style: none;
}

.agewrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.ålderInput {
  margin: 30px 0 35px;
  width: 100%;
}

.ålderInput .field {
  width: 100%;
  display: flex;
  align-items: center;
}

.field {
  width: 100%;
}

.field input {
  width: 100%;
  height: 100%;
  outline: none;
  margin-left: 12px;
  border: 1px solid rgb(90, 90, 90);
  text-align: center;
  font-size: 11pt;
  -moz-appearance: textfield;
  appearance: texfield;
}

input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
  -webkit-appearance: none;
  appearance: none;
}

.ålderInput .seperator {
  display: flex;
  justify-content: center;
  align-items: center;
}

.slider {
  margin-top: 20px;
  height: 5px;
  border-radius: 5px;
  background: gainsboro;
  position: relative;
}

.slider .progress {
  left: 25%;
  right: 25%;
  position: absolute;
  height: 5px;
  background: #83c5a7;
  border-radius: 5px;
}

.range-input {
  position: relative;
}

.range-input input {
  position: absolute;
  top: -7px;
  height: 5px;
  width: 100%;
  -webkit-appearance: none;
  appearance: none;
  pointer-events: none;
  background: none;
}

input[type="range"]::-webkit-slider-thumb {
  height: 12px;
  width: 12px;
  border-radius: 50%;
  -webkit-appearance: none;
  appearance: none;
  background: #83c5a7;
  pointer-events: auto;
}
input[type="range"]::-moz-range-thumb {
  height: 12px;
  width: 12px;
  border-radius: 50%;
  -moz-appearance: none;
  appearance: none;
  background: #83c5a7;
  pointer-events: auto;
}
.profiles {
  grid-column: 2;
  display: flex;
  flex-direction: column;
}
</style>
