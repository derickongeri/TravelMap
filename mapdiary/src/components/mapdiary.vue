<template>
  <div class="container">
    <div class="row">

        <div class="col-12">

          <h1 class="text-center text-info">Destination list</h1>

        </div>
        <!-- /.col-12 -->

    </div>
    <!-- /.row -->
    <div class="row">
       <div class="col-6">

         <townlist v-bind:towns="towns"/>

       </div>
       <!-- /.col-6 -->
       <div class="col-6">
         <destinationmap v-bind:map="map"/>

       </div>
       <!-- /.col-6 -->

    </div>
    <!-- /.row -->
  </div>
  <!-- /.container -->
</template>

<script>

  

  import axios from 'axios'
  import townlist from './townlist.vue'
  import Destinationmap from './destinationmap.vue'

export default {
  components: { townlist, Destinationmap },
  name: 'mapdiary',
  data: function (){ 
    return{
      towns: [],
    }
  },

  mounted: function() {
    
    axios.get('https://api.openbrewerydb.org/breweries')
        .then((r) => {
          this.towns = r.data;
        })

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
