<template>
  <div>
      <h2 class="card-title">Evolução das vendas</h2>
      <div class="col-sm-6">
        <button v-on:click="removeImpares">Remove os Impares</button>
      </div>
      <chartjs-line :labels="labels" :data="dataset" :bind="true" ></chartjs-line>
  </div>
</template>

<script>
export default {
  data(){
    return {
      labels: ['2010', '2011', '2012', '2013', '2014', '2015', '2016', '2017', '2018' , '2019', '2020'],
      dataset: [1000, 10000, 100000, 1000000, 10000000, 100000000, 1000000000, 10000000000, 100000000000, 1000000000000, 10000000000000],
      options: {
        title: {
          display: true,
          text: 'Evolução de Vendas'
        },
        legend: {
          display: false,
        }
      }
    };
  },
  methods: {
    removeImpares: function removeImpares() {
      let tamanho = this.labels.length -1 ;
      if(tamanho == 10)
      {
        for(let i = 0; i < tamanho ; i++)
        {
          if((this.labels[i] % 2) == 1)
          {
            this.dataset[i] = '';
            this.labels[i] = '';
          }
        }
        var dataset_pares = this.dataset.filter(function(el) {
          return el;
        });
        var labels_prares = this.labels.filter(function(el) {
          return el;
        });

        this.labels = labels_prares;
        this.dataset = dataset_pares;

      }else{
        var labels = ['2010', '2011', '2012', '2013', '2014', '2015', '2016', '2017', '2018' , '2019', '2020'];
        var dataset = [1000, 10000, 100000, 1000000, 10000000, 100000000, 1000000000, 10000000000, 100000000000, 1000000000000, 10000000000000];

        this.labels = labels;
        this.dataset = dataset;
      }



      //this.dataset.push(this.dataentry);
      //this.labels.push(this.datalabel);
      //this.datalabel = '';
      //this.dataentry = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
s
