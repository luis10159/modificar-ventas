<template>
  <div class="linea col-12"></div>
  <div class="row justify-center items-center q-mb-lg">
    <div class="col-12 text-center q-pb-sm">
      <q-toggle v-model="displayHtml5" label="Registrar guía de remisión" />
    </div>

    <div class="col-12 q-pb-xl">
      <div class="row text-center">
        <div class="col-12 q-pb-sm">
          <q-toggle v-model="displayHtml6" label="Registrar como anulada" />
        </div>
        <div class="col-6">
          <q-btn
            icon="delete_forever"
            label="Limpiar lista"
            stack
            glossy
            color="negative"
          />
        </div>
        <div class="col-6">
          <q-btn
            icon="save_as"
            label="Grabar (Ctrl+G)"
            stack
            glossy
            color="primary"
          />
        </div>
      </div>
    </div>
    <div class="col-8">
      <div class="row q-pl-sm">
        <div class="col-6 q-pr-sm">
          <q-input
            filled
            v-model="price9"
            label="Pagado con (F6)"
            mask="#.##"
            fill-mask="0"
            reverse-fill-mask
            input-class="text-right"
            color="white"
            bg-color="primary"
          />
        </div>
        <div class="col-6">
          <q-input
            filled
            v-model="price10"
            label="Vuelto"
            mask="#.##"
            fill-mask="0"
            reverse-fill-mask
            input-class="text-right"
            color="white"
            bg-color="negative"
          />
        </div>
      </div>
    </div>
  </div>

  <p>Campos importantes, no deben dejarse en blanco</p>
</template>

<script>
import { ref } from "vue";
export default {
  name: "filaC",

  setup() {
    return {
      displayHtml5: ref(false),
      displayHtml6: ref(false),
      price9: ref(null),
      price10: ref(null),
    };
  },
};
</script>

<style>
</style>