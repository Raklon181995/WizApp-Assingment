<template>
  <div >
    <v-app-bar>
      <v-app-bar-nav-icon 
      class="hidden-md-and-up"
       @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Wiz App</v-toolbar-title>

      <v-spacer></v-spacer>

      <div class="hidden-sm-and-down">
        
          <router-link class="text-decoration-none mx-7" to="/">Home</router-link>
          <router-link class="text-decoration-none mx-7" to="/services">Card Page</router-link>
          <router-link  class="text-decoration-none mx-7" to="/setting">Setting</router-link>
        
      </div>
      </v-app-bar>
      <v-navigation-drawer
      v-model="drawer"
      absolute
      left
      temporary
      width="75%"
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item>
           <router-link class="text-decoration-none mx-7" to="/">Home</router-link>
          </v-list-item>

          <v-list-item>
            <router-link class="text-decoration-none mx-7" to="/services">Card Page</router-link>
          </v-list-item>

          <v-list-item>
            <router-link  class="text-decoration-none mx-7" to="/setting">Setting</router-link>
          </v-list-item>

        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    
  </div>
</template>

<script>
  export default {
    data: () => ({
      drawer: false,
      group: null,
    }),

    watch: {
      group () {
        this.drawer = false
      },
    },
  }
</script>
<style scoped>
.router-link-exact-active {
  border-bottom: 2px solid #ed7607 !important;
}
</style>
