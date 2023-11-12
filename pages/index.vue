<script setup lang="ts">
const route = useRoute()
const hlaseniTextValue = ref('')
const speed = ref(10)
const cas = ref('b7')

const availableCasy = [{
  name: 'před 6. VH',
  value: 'b6'
}, {
  name: 'při 6. VH',
  value: 'i6',
}, {
  name: 'před 7. VH',
  value: 'b7'
}]

watch(hlaseniTextValue, (nvalue) => {
  console.log(nvalue);
})

const sendHlaseni = () => {
  console.log(hlaseniTextValue.value);
  alert({
    val: hlaseniTextValue.value,
    route: route
  })
}

</script>

<template>
  <div class="mainpage">
    <div class="hlaseni-input-container">
      <h5>Hlášený text</h5>
      <UTextarea v-model="hlaseniTextValue" />
      <br>
      <h5>Rychlost mluvy</h5>
      <span> {{ (speed / 10).toFixed(1) }} </span>
      <URange :min="5" :max="20" :step="5" v-model="speed" />
      <br>
      <USelect v-model="cas" :options="availableCasy" option-attribute="name" />

      <br>
      <UButton @click="sendHlaseni">Odeslat</UButton>
    </div>
  </div>
</template>

<style lang="scss">
.hlaseni-input-container {
  display: flex;
  flex-direction: column;
  align-items: left;
  justify-content: center;
  margin: 3rem auto;
  height: 100%;
  max-width: 20rem;
}
</style>
