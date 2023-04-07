<template>
  <q-page class="flex flex-center">
    <div class="q-pa-md q-gutter-sm">
      <q-btn
        label="Modificar venta"
        icon="keyboard_arrow_right"
        color="primary"
        @click="open('right')"
      />

      <q-dialog v-model="dialog" :position="position" maximized>
        <q-card class="column full-height">
          <q-card-section class="row items-center no-wrap">
            <div class="q-pa-md">
              <p class="col-6 text-h6 text-weight-bold text-center">
                Ventas de productos
              </p>
              <p class="col-6 text-subtitle2">Cod de venta: #</p>
              <div class="q-mb-lg">
                <q-radio size="xs" v-model="shape" val="xs" label="Pro" />
              </div>

              <q-btn
                label="Resetear"
                push
                color="white"
                text-color="primary"
                @click="reset"
                class="q-mb-md"
              />

              <q-stepper
                v-model="step"
                header-nav
                ref="stepper"
                color="primary"
                animated
                style="max-width: 840px"
              >
                <q-step :name="1" title="Paso 1" icon="settings" :done="done1">
                  <!-- parte 1 -->

                  <filaA></filaA>

                  <q-stepper-navigation>
                    <q-btn
                      @click="
                        () => {
                          done1 = true;
                          step = 2;
                        }
                      "
                      color="primary"
                      label="Continuar"
                    />
                  </q-stepper-navigation>
                </q-step>

                <q-step
                  :name="2"
                  title="Paso 2"
                  icon="create_new_folder"
                  :done="done2"
                >
                  <!-- parte 2 -->
                  <filaB></filaB>

                  <!-- parte 3 -->

                  <filaC></filaC>
                  <q-stepper-navigation>
                    <q-btn
                      @click="
                        () => {
                          done2 = true;
                          step = 3;
                        }
                      "
                      color="primary"
                      label="Continuar"
                    />
                    <q-btn
                      flat
                      @click="step = 1"
                      color="primary"
                      label="Volver"
                      class="q-ml-sm"
                    />
                  </q-stepper-navigation>
                </q-step>

                <q-step
                  :name="3"
                  title="Paso 3"
                  icon="add_comment"
                  :done="done3"
                  class=""
                >
                  <!-- parte 4 -->
                  <filaD></filaD>
                  <!-- parte 5 -->
                  <filaE></filaE>
                  <q-stepper-navigation>
                    <q-btn
                      color="primary"
                      @click="done3 = true"
                      label="Finalizar"
                    />
                    <q-btn
                      flat
                      @click="step = 2"
                      color="primary"
                      label="Volver"
                      class="q-ml-sm"
                    />
                  </q-stepper-navigation>
                </q-step>
              </q-stepper>
            </div>
          </q-card-section>
        </q-card>
      </q-dialog>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";

import filaA from "components/filaA.vue";
import filaB from "components/filaB.vue";
import filaC from "components/filaC.vue";
import filaD from "components/filaD.vue";
import filaE from "components/filaE.vue";

// table

export default defineComponent({
  name: "IndexPage",
  components: {
    filaA,
    filaB,
    filaC,
    filaD,
    filaE,
  },

  setup() {
    // dialog
    const dialog = ref(false);
    const position = ref("right");
    // stepper
    const step = ref(1);
    const done1 = ref(false);
    const done2 = ref(false);
    const done3 = ref(false);

    return {
      // dialog
      dialog,
      position,

      open(pos) {
        position.value = pos;
        dialog.value = true;
      },
      // stepper
      step,
      done1,
      done2,
      done3,
      reset() {
        done1.value = false;
        done2.value = false;
        done3.value = false;
        step.value = 1;
      },
      // toggle
      displayHtml: ref(false),

      //table

    // hgf
    shape: ref('line'),
    };
  },
});
</script>

<style>
.linea {
  padding: 5px;
  background-color: rgba(31, 59, 85, 0.096);
}



</style>