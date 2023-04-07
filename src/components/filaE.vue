<template>
  <div class="linea col-12"></div>
  <div class="row justify-center items-center q-mb-lg">
    <div class="col-12 text-center q-pb-sm">
      <q-radio
        size="xs"
        v-model="shape"
        val="xs"
        label="Registrar guía de remisión"
      />
    </div>

    <div class="col-12 q-pb-xl">
      <div class="row text-center">
        <div class="col-12 q-pb-sm">
          <q-radio
            size="xs"
            v-model="shape2"
            val="xs"
            label="Registrar como anulada"
          />
        </div>
      </div>
    </div>
    <div class="col-2">
      <q-fab
        v-model="fabCenter"
        vertical-actions-align="center"
        color="primary"
        glossy
        icon="keyboard_arrow_up"
        direction="up"
      >
        <q-fab-action
          color="primary"
          @click="onClick"
          icon="save"
          label="Guardar"
        />
        <q-fab-action
          color="negative"
          @click="onClick"
          icon="delete"
          label="Eliminar L"
        />
      </q-fab>
    </div>

    <div class="col-9">
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
      shape: ref("line"),
      shape2: ref("line"),

      fabLeft: ref(true),
      fabCenter: ref(true),
      fabRight: ref(true),
    };
  },
};
</script>

<style>
</style>