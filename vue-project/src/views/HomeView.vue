<template>
  <div class="centered">
    <h1>Selecciona un número del 1 al 9:</h1>
    <div class="grid">
      <button v-for="number in numbers" :key="number" @click="selectNumber(number)">
        {{ number }}
      </button>
    </div>
    <p v-if="selectedNumber">Has seleccionado el número {{ selectedNumber }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      selectedNumber: null
    };
  },
  methods: {
    selectNumber(number) {
      this.selectedNumber = number;
    }
  }
};
</script>

<style>
.centered {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
  margin-top: 20px;
}

button {
  margin: 5px;
}
</style>
