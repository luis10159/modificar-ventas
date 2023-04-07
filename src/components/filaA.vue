<template>
  <p class="text-weight-bold">Lista de productos</p>
  <q-virtual-scroll
    type="table"
    style="max-height: 45vh"
    :virtual-scroll-item-size="48"
    :virtual-scroll-sticky-size-start="48"
    :virtual-scroll-sticky-size-end="32"
    :items="heavyList"
  >
  
    <template v-slot:before>
      
      <thead class="">
        <tr>
          <th v-for="col in columns" :key="'1--' + col.name2">
            {{ col.name1 }}
          </th>
          <th>Editar</th>
          <th>Eliminar</th>
        </tr>
        <tr>
          <th v-for="col in columns" :key="'2--' + col.name2">
            {{ col.name2 }}
          </th>
          <th>-</th>
          <th>-</th>
        </tr>
      </thead>
    </template>

    <template v-slot="{ item: row, index }">
      <tr :key="index">
        <td v-for="col in columns" :key="index + '-' + col.name2">
          {{ row[col.prop] }}
        </td>
        <td>
          <q-btn icon="edit" color="primary" @click="open('right')" />
        </td>
        <td>
          <q-btn icon="delete" color="negative" @click="open('right')" />
        </td>
      </tr>
    </template>
  </q-virtual-scroll>
</template>

<script>
import { ref } from "vue";

const rows = [
  {
    item: 1,
    cantidad: 2,
    name: "Sporade",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 5,
    name: "Tomate",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Lechuga",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
  {
    item: 1,
    cantidad: 3,
    name: "Pimiento",
    unidad: 159,
    precio: 159,
    total: 159,
    codbarra: "|||||||",
    icbper: 159,
  },
];

const columns = [
  { name1: "(#)", name2: "Item", prop: "item" },
  { name1: "(#)", name2: "Cantidad", prop: "cantidad" },
  { name1: "(#)", name2: "producto", prop: "name" },
  { name1: "(#)", name2: "Unidad", prop: "unidad" },
  { name1: "(s/)", name2: "Precio", prop: "precio" },
  { name1: "(s/)", name2: "Total", prop: "total" },
  { name1: "(#)", name2: "CodBarra", prop: "codbarra" },
  { name1: "(#)", name2: "ICBPER", prop: "icbper" },
];

const heavyList = [];

Array.prototype.push.apply(heavyList, rows);

export default {
  name: "filaA",

  setup() {
    return {
      heavyList,
      columns,
    };
  },
};
</script>

<style lang="sass">
.thead-custom-sticky tr > *,
.tfoot-custom-sticky tr > *
  position: sticky
  opacity: 1
  z-index: 1
  background-color: black
  color: white

.thead-custom-sticky tr:last-child > *
  top: 0

.tfoot-custom-sticky tr:first-child > *
  bottom: 0
</style>