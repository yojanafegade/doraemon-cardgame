<template>
  <div class="app-container">
    <HeaderItem/>
    <FlipCard />
  </div>
</template>

<script>
import FlipCard from './components/FlipCard.vue';
import HeaderItem from './components/HeaderItem.vue';

export default {
  components: {
    FlipCard,
    HeaderItem,
  },
};
</script>

<style>
/* Apply Tailwind CSS classes if needed */
@import url('https://fonts.googleapis.com/css2?family=Open+Sans&family=Poppins:wght@500&display=swap');


body{
  margin: 0;padding: 0;
   overflow-x: hidden;
  overflow-y:hidden ;
  font-family: 'Poppins', sans-serif;
}
.app-container{
  
  background-color: #070921;
}


</style>

