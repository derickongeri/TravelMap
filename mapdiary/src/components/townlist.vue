<template>
    <div class="card  towns-list">
          <ul class="list-group list-group-flush">
            <li 
              
              v-for="town in towns" v-bind:key="town"
              class="list-group-item">{{town.name}}, {{town.state}}</li>
          </ul>
         </div>
</template>

<script>
export default {
    name: "townlist",
    props: {
        towns: Array
    } 
}
</script>

<style lang="scss" scoped>

    .towns-list{

      overflow-y: scroll;
      height: 95vh;
      li {
        &:hover{
          background-color: darkgray;
        }
      }
    }
</style>