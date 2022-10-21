<template>
    <h1>Lager</h1>

<table>
    <tr>
        <th>Produktnr</th>
        <th>Namn</th>
        <th>Kategori</th>
        <th>Lagersaldo</th>
        <th>Pris</th>
        <th>Radera</th>
        <th>Ändra</th>
    </tr>

<!-- Loopar igenom-->
<!--Lyssnar efter emit med @deleteVitamin @deleteVitamin="deleteVitamin(vitamin.id)"-->
    <Vitamin @deleteVitamin="deleteVitamin(vitamin.id)" v-for="vitamin in vitamins" :vitamin="vitamin" :key="vitamin.id" />

</table>
   </template>

    <script>
import Vitamins from "../components/Vitamins.vue";

export default {
       // Reaktiv data, fyller på med data från webbtjänsten
       data() {
        return {
            vitamins: []
        }
       },
    
    components: {
        Vitamins
    },

    methods: {
       //GET books
    async getVitamins() {

    //Fetch till restwebbtjänst
    const resp = await fetch("http://localhost:8000/api/vitamins"); 

    // När vi fått svar från webbtjänsten ska data lagras
    const data = await resp.json();

    this.vitamins = data; 
    }
},
    async deleteVitamin(id){
        const resp = await fetch("http://localhost:8000/api/vitamins/" + id, {
            //Deleteanrop
            method: "DELETE",
            //Headers
            headers:{
                "Accept": "application json",
                "Content-Type": "application/json"

            }
        });

        const data = await resp.json();

        //Läs in böcker på nytt
        this.getVitamins();
   }, 

//När komponenten laddas in kommer funktionen köras
mounted() {
    this.getVitamins();
}
}



</script>
<style scoped>
h1 {
    text-align: center;
    margin-bottom:2%;
    margin-top:2%;
}</style>