<template>

<!-- mustascher för att hämta vitaminer-->
<!-- Eventlyssnare @-->
<!-- Emit till föräldrakomponenten -->

<tr> 
    <td v-bind:id="'productno' +vitamin.id" contenteditable>{{vitamin.productno}}</td>
    <td v-bind:id="'name' + vitamin.id" contenteditable>{{vitamin.name}}</td>
    <td v-bind:id="'category' +vitamin.id" contenteditable>{{vitamin.category}}</td>
    <td v-bind:id="'amount' +vitamin.id" contenteditable> {{vitamin.amount}}  </td>
    <td v-bind:id="'price' +vitamin.id" contenteditable> {{vitamin.price}}</td>
    <td @click="$emit('deleteVitamin')">Radera</td>
    <td @click="$emit('updateVitamin')">Ändra</td>
  </tr> 


</template>

<script>
export default {
    props: {
        vitamin: Object
    }
}
</script>


<style scoped>
.button {
  background-color: #ddd;
  border: none;
  color: black;
  padding: 5px 15px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 30px;
}</style>
