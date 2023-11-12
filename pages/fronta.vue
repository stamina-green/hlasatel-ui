<script setup lang="ts">
const fronta = [
    {
        time: new Date("10/11/23"),
        text: "Opustte skolu! Uz je opet ten cas roku",
        state: 3
    },
    {
        time: new Date(),
        text: "Pan zastupce reditele Ruzicka ziskal doktorat. Timto dekuje jeho online skole.",
        state: 2
    },
    {
        time: new Date("12/11/23"),
        text: "Reditel skoly odvolava vyhlasky ministra skolstvi protoze muze",
        state: 1
    }
]

const states = [
     {
        name: "Čeká na vyhlášení",
        color: "blue"
    },
     {
        name: "Hlásí se",
        color: "green"
    },
    {
        name: "Již vyhlášeno",
        color: "grey"
    }
]

</script>

<template>
  <div class="frontapage">
    <div class="fronta-container">
      <h1>Fronta</h1>
      <br>
      <div v-for="(element, i) in fronta" :key="i">
        <UCard class="card" :style="`border-color: ${states[element.state - 1].color}`">
            <template #header>
                <div class="header">
                    {{ states[element.state - 1].name }}
                </div>
            </template>

            {{ element.text }}

            <template #footer>
                <div class="footer">
                    {{ element.time.toLocaleString('cs-CZ') }}
                </div>
            </template>
        </UCard>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.fronta-container {
  display: flex;
  flex-direction: column;
  align-items: left;
  justify-content: center;
  margin: 3rem auto;
  height: 100%;
  max-width: 20rem;
}

.card {
    margin: 1rem 0rem;
    border: 2px solid;
}

.header {
    font-size: 1.7rem;
}
</style>
