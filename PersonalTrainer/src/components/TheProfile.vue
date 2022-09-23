<script setup></script>

<template>
  <div class="boxGroup">
    <div v-for="Trainer in Trainers" :key="Trainer.ID" class="box">
      <div class="boxHeader">
        <span>{{ Trainer.Name }}</span>
      </div>
      <div class="boxContent">
        <span>
          <div>
            <span>Credentials: {{ Trainer.Credentials }}</span>
            <p>{{ Trainer.Description }}</p>
            <p>Age: {{ Trainer.Age }}</p>
            <p>Price: {{ Trainer.Price }}kr</p>
          </div>
        </span>
      </div>
      <div class="boxFooter">
        <span>Placeholder for ratings</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.box {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto 2fr auto;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  width: 500px;
  height: 300px;
  margin-bottom: 18%;
  border: 2px solid black;
  box-shadow: #83c5a7 0px 54px 55px, #83c5a7 0px -12px 30px, #83c5a7 0px 4px 6px,
    #83c5a7 0px 12px 13px, #83c5a7 0px -3px 5px;
}

.boxHeader {
  grid-row: 1;
  border-bottom: 2px ridge #7c3a58;
  padding: 1%;
}

.boxContent {
  grid-row: 2;
  border-bottom: 2px ridge #7c3a58;
  padding: 1%;
}
.boxFooter {
  grid-row: 3;
  padding: 1%;
}
</style>

<script>
const Value = {
  fatBurn: 1,
  growMuscles: 2,
  improveEndurance: 3,
  betterBoxing: 4,
};
export default {
  data() {
    return {
      Trainers: [
        {
          ID: 0,
          Name: "Lucas",
          Credentials: "Nordic Master of Weightlifting",
          Age: 18,
          Price: 200,
          Goal: Value.growMuscles,
          Description:
            "I am the youngest man in nordic history to win the nordic championship. I want to help people be stronger than ever.",
        },
        {
          ID: 1,
          Name: "Samuel",
          Credentials: "Hunter From the Swedish Military",
          Age: 19,
          Price: 5000,
          Goal: Value.improveEndurance,
          Description:
            "I am one of the youngest accomplished military men ever and started working as a personal trainer to help people improve their mental fortitude and their endurance.",
        },
        {
          ID: 2,
          Name: "Sebbe",
          Credentials: "Strongest man alive, also a web developer",
          Age: 36,
          Price: 30000,
          Goal: Value.improveEndurance,
          Description:
            "I am quite litteraly the strongest man alive. There is not a single being on this earth that could compare to my prowess. But you already knew that.",
        },
        {
          ID: 3,
          Name: "Albin",
          Credentials: "Fastest student in the world",
          Age: 19,
          Price: 5000,
          Goal: Value.fatBurn,
          Description:
            "My philosophy consists of nothing but speed. That is my motto. I am the best choice of personal trainer for you if you're aiming to gain speed and lose fat since if you go fast enough you're bound to lose fat.",
        },
        {
          ID: 4,
          Name: "Marcus",
          Credentials: "Fastest walker in the world",
          Age: 19,
          Price: 5000,
          Goal: Value.improveEndurance,
          Description:
            "I walk several 100s of kilometers everyday to school. I am the man your grandparents fear; My walk to school was worse than theirs",
        },
      ],
    };
  },
};
</script>
