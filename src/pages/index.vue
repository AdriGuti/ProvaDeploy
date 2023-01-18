<template>
  <v-container fluid>
    <v-row >
      <v-col style="background-color:rgb(37, 147, 73);" align="center">
        <h1>PREU</h1>
        <v-text-field type="number" v-model="preu" color="white" style="max-width:400px" outlined rounded></v-text-field>
        <h1>COST</h1>
        <v-text-field type="number" v-model="cost" color="white" style="max-width:400px" outlined rounded></v-text-field>
      </v-col>
      <v-col style="background-color:rgb(37, 147, 73);" align="center">
        <p>
          "El client paga {{ preu }} euros per un producte.
          <br>
          L'estat es queda impostos per valor de {{IVA}} euros (21% d'IVA)
          <br>
          El producte ha costa {{cost}}.
          <br>
          Per tant el marge que et queda a tu com a venedor és de {{ benefici }} euros."  
        </p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default{
    computed:{
      IVA(){
        return (parseFloat(this.preu)*0.21).toFixed(2)
      },
      benefici(){
        return (parseFloat(this.preu)*0.89-this.cost).toFixed(2)
      }
    },
    data(){
      return{
        preu:10,
        cost:5,
      }
    }
  }
</script>