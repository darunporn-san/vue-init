<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div class="px-10 flex items-center">
      <button
        class="h-10 px-4 font-semibold rounded-md bg-black text-white mr-5"
        @click="decrease"
      >
        -
      </button>
      <p>count : {{ counter }}</p>
      <button
        class="h-10 px-4 font-semibold rounded-md bg-black text-white ml-5"
        @click="increment"
      >
        +
      </button>
    </div>
  </div>
</template>

<script>
import { useCounterStore } from "@/stores/counter";
import { toRefs } from "vue";

export default {
  setup() {
    const counterStore = useCounterStore();
    const { counter, increment, decrease } = toRefs(counterStore);
    return {
      counter,
      increment,
      decrease,
    };
  },
};
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
