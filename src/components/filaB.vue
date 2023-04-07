<template>
  <div class="row justify-center items-center">
    <div class="col-3 q-pr-sm">
      <q-input
        filled
        v-model="price"
        label="Importe Bruto"
        mask="#.##"
        fill-mask="0"
        reverse-fill-mask
        input-class="text-right"
      />
    </div>
    <div class="col-3 q-pr-sm">
      <q-input
        filled
        v-model="price2"
        label="Trans. Grat"
        mask="#.##"
        fill-mask="0"
        reverse-fill-mask
        input-class="text-right"
      />
    </div>
    <div class="col-3 q-pr-sm">
      <div class="col">
        <q-input
          filled
          v-model="price3"
          label="Desc"
          mask="#.##"
          fill-mask="0"
          reverse-fill-mask
          input-class="text-right"
        />
      </div>
      <div class="col q-mt-xs">
        <q-input
          filled
          v-model="price4"
          mask="#.##"
          fill-mask="0"
          reverse-fill-mask
          input-class="text-right"
        />
      </div>
    </div>
    <div class="col-3 q-pr-sm">
      <q-input
        filled
        v-model="price5"
        label="Sub Total"
        mask="#.##"
        fill-mask="0"
        reverse-fill-mask
        input-class="text-right"
      />
    </div>
    <div class="col-4 q-pr-sm">
      <div class="col">
        <q-radio size="xs" v-model="shape" val="xs" label="IGV 18%" />
      </div>
      <div class="col">
        <q-input
          filled
          v-model="price6"
          mask="#.##"
          fill-mask="0"
          reverse-fill-mask
          input-class="text-right"
        />
      </div>
      <div class="col">
        <q-radio size="xs" v-model="shape2" val="xs" label="Deducir IGV" />
      </div>
    </div>
    <div class="col-4 q-pr-sm">
      <q-input
        filled
        v-model="price7"
        label="ICBPEF"
        mask="#.##"
        fill-mask="0"
        reverse-fill-mask
        input-class="text-right"
      />
    </div>
    <div class="col-4">
      <q-input
        filled
        v-model="price8"
        label="Valor Total"
        mask="#.##"
        fill-mask="0"
        reverse-fill-mask
        input-class="text-right"
      />
    </div>
  </div>
  <div class="linea col-12"></div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "filaB",

  setup() {
    return {

      price: ref(null),
      price2: ref(null),
      price3: ref(null),
      price4: ref(null),
      price5: ref(null),
      price6: ref(null),
      price7: ref(null),
      price8: ref(null),

      shape: ref('line'),
      shape2: ref('line'),
    };
  },
};
</script>
