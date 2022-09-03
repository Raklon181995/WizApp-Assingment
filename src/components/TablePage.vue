<template>
<div align="center">
    <div v-if="loading" class="loader"></div>
    <div class="pt-4 d-flex">
     <template>
        <v-text-field
          v-model="search"
          label="Search by Name"
          class="mx-4"
          append-icon="mdi-magnify"
          outlined   dense
        ></v-text-field>
      </template>
        </div>

    <v-simple-table  fixed-header  height="440px">
      <thead>
        <tr>
          <th class="font-15 text-left sticky-col first-col">
           Name
          </th>
          <th class="font-15  text-left">
            Description
          </th>
           <th class="font-15 text-left">
            Auth
          </th>
          <th class="font-15  text-left">
            Category
          </th>
          <th class="font-15 text-left">
            Cors
          </th>
          <th class="font-15 text-left">
              HTTP
          </th>
          <th class="font-15 text-left">
            Links
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="entery in filterArray" :key="entery" class="post"
        >
          <td class="sticky-col first-col">{{ entery.API }}</td>
          <td>{{ entery.Description }}</td>
          <td>{{ entery.Auth }}</td>
          <td>{{ entery.Category }}</td>
          <td>{{ entery.Cors }}</td>
          <td>{{ entery.HTTPS }}</td>
          <td>{{ entery.Link }}</td>
        </tr>
      </tbody>
  
    </v-simple-table>       
</div>
</template>

<script>
import axios from 'axios';


export default {
    name: 'consume-rest-api',
    data(){
        return{
            entries: null,
            loading: false,
            search: '',
            filter: {
              name: '',
              },
        }
    },
     computed:{
        filterArray:function(){
            return this.entries.filter((entery)=>{
                return entery.API.match(this.search);
            });
        }
    },

    created() {
        this.loading = true;
        axios.get(`https://api.publicapis.org/entries`)
            .then(response => {
                // JSON responses are automatically parsed.
                this.entries = response.data.entries
                console.log(this.entries);
                this.loading = false
            })
            .catch(e => {
                this.errors.push(e)
                this.loading = false
            });
    }
}
</script>

<style lang="scss" scoped>
.font-15 {
  font-size: 16px !important;
}
.loader {
  border: 16px solid #f3f3f3;
  border-top: 16px solid #3498db;
  border-radius: 50%;
  width: 36px;
  height: 36px;
  animation: spin 2s linear infinite;
}
.sticky-col {
  position: -webkit-sticky !important;
  position: sticky !important;
  background-color: white;

}
.first-col {
  width: 200px !important;
  min-width: 100px !important;
  max-width: 100px !important;
  left: 0px !important;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>