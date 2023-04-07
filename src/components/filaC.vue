<template>
  <div class="row justify-center items-center">
    <p class="col-12 text-weight-bold text-center q-py-md">Datos del cliente</p>
    <div class="col-4 q-pr-sm q-pb-sm">
      <q-select
        class="text-center"
        label="Cliente"
        transition-show="jump-up"
        transition-hide="jump-up"
        filled
        v-model="model"
        :options="options"
      />
    </div>
    <div class="col-2 text-center q-pr-sm q-pb-sm">
      <q-btn color="teal">
        <q-icon left size="3em" name="group" />
        <div>
          Cliente <br />
          (F2)
        </div>
      </q-btn>
    </div>
    <div class="col-3 q-pr-sm q-pb-sm">
      <q-input
        filled
        v-model="text"
        label="RUC/DNI"
        stack-label
        :dense="dense"
      />
    </div>
    <div class="col-3 q-pr-sm q-pb-sm">
      <q-select
        label="Dirección"
        transition-show="jump-up"
        transition-hide="jump-up"
        filled
        v-model="model2"
        :options="options"
      />
    </div>
    <div class="col-4 q-pr-sm q-pb-sm">
      <q-input
        filled
        v-model="text2"
        label="Crédito S/"
        stack-label
        :dense="dense"
      />
    </div>

    <div class="col-4 q-pr-sm q-pb-sm">
      <q-input
        filled
        v-model="text3"
        label="Persona/Dirección de entrega"
        stack-label
        :dense="dense"
      />
    </div>
    <div class="col-4 text-center q-pr-sm q-pb-sm">
      <q-select
        label="Dirección"
        transition-show="jump-up"
        transition-hide="jump-up"
        filled
        v-model="model3"
        :options="options"
      />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "filaC",

  setup() {
    return {
      options: ["Opción 1", "Opción 2", "Opción 3", "Opción 4", "Opción 5"],
      dense: ref(false),
      text: ref(""),
      text2: ref(""),
      text3: ref(""),
      model: ref(null),
      model2: ref(null),
      model3: ref(null),
    };
  },
};
</script>

<style>
</style>