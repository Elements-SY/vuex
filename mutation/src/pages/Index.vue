<template>
    <div class="container">
      <ul>
          <li v-for="product in saleProducts">
              <span>{{product.name}}</span>
              <span>{{product.price}}</span>
          </li>
      </ul>
       <button @click="reduce">走起</button>
    </div> 
</template>
<script>
 export default{
   computed:{
       saleProducts(){
           return this.$store.getters.saleProducts;
       }
   },
   methods:{
       reduce(){
          this.$store.commit('reducePrice');
       }    
   }
 }

</script>
<style scoped>
.container{
 width: 400px;
 height: 400px;
 border: 1px solid #000;
 line-height: 40px;
 margin: 100px auto;
}


</style>
