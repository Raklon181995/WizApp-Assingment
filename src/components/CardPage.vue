<template>
  <div>
      <template>
        <v-text-field
          v-model="search"
          label="Search by Name"
          class="mx-4"
          append-icon="mdi-magnify"
          outlined   dense
        ></v-text-field>
      </template>
    <v-row>
        <v-col cols="6" md="3" 
          v-for="cardDetail in filterArray" :key="cardDetail"> 
              <v-card class="mt-6" max-width="300"
  >
      <v-img
        class="white--text align-end"
        height="200px"
        src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      >
        <v-card-title>Company Name</v-card-title>
      </v-img>

      <v-card-subtitle class="pb-0">
       Name: {{ cardDetail.name}}
      </v-card-subtitle>

      <v-card-text class="text--primary">
        <div>Emp Id: {{ cardDetail.id}}</div>

        <div>Salary: {{ cardDetail.salary }}</div>
      </v-card-text>

      <v-card-actions>
        <v-btn color="orange" text @click="removeCard()">
          Delete
        </v-btn>
      </v-card-actions>
    </v-card>
        </v-col>
    </v-row>
  
  </div>
</template>

<script>
// import axios from "axios";

export default {
  name: "consume-rest-api",
  data() {
    return {
       search: '',
            filter: {
              name: '',
              },
      cardDetails: [
          {name:"Rakesh",id:"1",salary:"50,000"},
          {name:"Akshata",id:"2",salary:"50,000"},
          {name:"Yogesh",id:"3",salary:"50,000"},
          {name:"Vinayak",id:"4",salary:"50,000"},
          {name:"Nagesh",id:"5",salary:"50,000"},
          {name:"Mayur",id:"6",salary:"50,000"},
          {name:"Viraj",id:"",salary:"50,000"},
          ]
    };
    
  },
   computed:{
        filterArray:function(){
            return this.cardDetails.filter((cardDetail)=>{
                return cardDetail.name.match(this.search);
            });
        }
    },

//   created() {
//     axios
//       .get(`https://material.io/components/cards`)
//       .then(response => {
//         // JSON responses are automatically parsed.
//         this.cards = response.data.cards;
//       })
//       .catch(e => {
//         this.errors.push(e);
//       });
//   }
};
</script>

<style scoped></style>
