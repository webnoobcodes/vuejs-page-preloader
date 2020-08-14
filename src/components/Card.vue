<template>
  <div class="card" :class="gridClass" :style="gridStyle"></div>
</template>

<script>
  export default {
    props: [
      'item',
    ],
    computed: {
      gridStyle() {
        return {
          'background-image': 'url('+ require('../assets'+ this.item.img) +')' };
      },
      gridClass() {
        return { 
          'card-1-1': this.item.grid === 'card-1-1',
          'card-2-1': this.item.grid === 'card-2-1'
        };
      }
    }
  }
</script>

<style lang="scss" scoped>
  .card {
    width: 100%;
    height: 200px;
    background-position: center;
    background-size: cover;
  }

  .card-1-1 {
    grid-column: span 1;
  }

  .card-2-1 {
    grid-column: span 2;
  }  
</style>