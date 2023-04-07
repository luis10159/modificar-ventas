<template>
  <div class="row justify-center items-center q-mb-lg q-pt-sm">
    <div class="col-12 q-pr-xl">
      <p class="text-weight-bold">Documento de venta</p>
      <div class="row justify-center items-center q-mb-lg">
        <div class="col-6 q-pr-sm q-pb-sm">
          <q-select
            label="Boleta de venta S1"
            transition-show="jump-up"
            transition-hide="jump-up"
            filled
            v-model="model4"
            :options="options"
          />
        </div>
        <div class="col-2 q-pr-sm q-pb-sm">
          <q-input filled v-model="text4" stack-label  />
        </div>
        <div class="col-4 q-pb-sm">
          <q-input filled v-model="text5" stack-label  />
        </div>
      </div>
    </div>
    <div class="linea col-12"></div>
    <div class="col-12 q-pr-xl">
      <p class="q-my-none text-weight-bold">Nro de pedido</p>
      <div class="row justify-center items-center">
        <div class="col-3 q-pr-sm q-pb-sm">
          <q-input filled v-model="text6" stack-label  />
        </div>
        <div class="col-5 q-pr-sm q-pb-sm">
          <q-input filled v-model="text7" stack-label  />
        </div>
        <div class="col-4 q-pb-sm">
          <q-toggle
            class="col-3 self-center"
            v-model="displayHtml4"
            label="Sin F. Emisión"
          />
          <q-input v-model="date" filled type="date" />
        </div>
      </div>
    </div>
    <div class="linea col-12"></div>
    <div class="col-12 q-pb-sm">
      <p class="text-weight-bold">Medio (f5)</p>

      <q-select
        class="q-mb-lg"
        label="Contado"
        transition-show="jump-up"
        transition-hide="jump-up"
        filled
        v-model="model5"
        :options="options"
      />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "filaD",

  setup() {
    return {
      text4: ref(""),
      text5: ref(""),
      text6: ref(""),
      text7: ref(""),
      displayHtml4: ref(false),
      date: ref(""),
      model4: ref(null),
      model5: ref(null),
      options: ["Opción 1", "Opción 2", "Opción 3", "Opción 4", "Opción 5"],
    };
  },
};
</script>

<style>
</style>