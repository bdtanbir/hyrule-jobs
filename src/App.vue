<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="Logo" />
        <h1>Hyrul Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order by Title</button>
        <button @click="handleClick('salary')">Order by Salary</button>
        <button @click="handleClick('location')">Order by Location</button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobsList from "./components/JobsList.vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: {
    JobsList,
  },
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "farm worker",
        location: "lon lon ranch",
        salary: 30000,
        id: "1",
        description:
          "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo, ex ad. Facere rem fugiat eos, quae officiis veniam tempore minus cum voluptates magnam ipsa eligendi aspernatur, eius saepe vero?",
      },
      {
        title: "querryman",
        location: "death mountain",
        salary: 40000,
        id: "2",
        description:
          "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Saepe sit nemo recusandae reprehenderit ducimus illum doloribus aperiam rerum nihil!",
      },
      {
        title: "flute player",
        location: "the lost woods",
        salary: 35000,
        id: "3",
        description:
          "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Architecto fugit assumenda  provident, hic facilis tenetur libero exercitationem consequatur eligendi excepturi veniam quae ullam ipsum laboriosam, sunt maxime.",
      },
      {
        title: "fisherman",
        location: "lake hylia",
        salary: 21000,
        id: "4",
        description:
          "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Beatae, minus voluptatem reiciendis labore molestias corrupti eligendi doloribus voluptates nesciunt quis!",
      },
      {
        title: "prison guard",
        location: "gerudo valley",
        salary: 32000,
        id: "5",
        description:
          "Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora sed ea dicta animi aspernatur quaerat deserunt et ad placeat mollitia?",
      },
    ]);
    const order = ref<OrderTerm>("title");
    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleClick, order };
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title {
  display: flex;
  justify-content: center;
}
header img {
  width: 60px;
  margin-right: 20px;
}
header h1 {
  font-size: 3em;
}
</style>
