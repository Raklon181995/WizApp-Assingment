<template>
 <div id="app">
   <v-container>
     <div class="text-center"><h1>Table Page</h1></div>
   </v-container>
    <TablePage />
 </div>
</template>

<script>
import TablePage from "@/components/TablePage.vue";
  export default {
    name: 'Home',

    components: {
      TablePage
    },
  }
</script>
<style lang="scss" >
// @import "@/assets/Scss/_main.scss";
.mainClass {
  padding-top: 0px !important;
}
.text-section{
  top: 50% !important;
}
.text-title{
  font-size: 18px;
  font-weight: 550;
  color: rgb(144, 172, 209);
}
.name{
  font-size: 35px;
  font-weight: 800;
}
.job{
  font-size: 20px;
  font-weight: 400;
  color: red;
}
.sub-title{
  font-size: 12px;
  color: gray;
}
.all-button{
  background-color: rgb(144, 172, 209) !important;
  color: white !important;
}
</style>

