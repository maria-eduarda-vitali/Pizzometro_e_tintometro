<!-- 1 -->
<template>
  <div class="container">
    <div class="row">
      
      <div class="col-md-4 mb-5">
        <img alt="tinta" src="tinta.png" width="350" height="300" />
      </div>
      <!-- fim da imagem -->

      <div class="col-md-7">

            <h1>Cálculo de tinta</h1>
            <p>
              Calcule quantas latas de tinta será preciso para a sua reforma por m²!
            </p>

            <div class="mb-3">
              <label class="form-label"> Area: </label>
              <input class="form-control" type="text" v-model="area" />
            </div>
          
            <button class="btn btn-primary my-3" v-on:click="calcular()" > calcular </button>
            
      </div>
      <!-- fim do formulário -->

    </div>

    <div class="row">
      <div class="offset-md-4 col-md-8">
        <!-- area para exibir as variáveis -->

        <p> Quantidade de lata: {{latas}}</p>
        <p> Preço: {{preco}} </p>
      </div>
    </div>
  </div>
</template>

<!-- 2 -->
<script>
  export default {
    name : 'App',
    data(){
      return {
          area: 0,
          litro: 0,
          latas: 0,
          preco: 0
      }
    },

  methods:{
   calcular(){

    let quantaTintaFalta

     this.litro = this.area / 6;

     this.latas = parseInt((this.litro) / 18);

     quantaTintaFalta = parseInt(this.latas) % 18;

        if(quantaTintaFalta > 0){
          this.latas++
        }

      this.preco = this.latas * 80.00;
      }

  }
}
</script>

<!-- 3 -->
<style>
  @import "https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css";
</style>
