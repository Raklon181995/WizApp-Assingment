<template>
  <div id="app">
    <v-app>
      <div v-if="$route.path != '/'"></div>
      <Header />
      <v-main>
        <v-container fluid>
          <v-row class="fill-height">
            <v-col>
              <transition name="fade">
                <router-view></router-view>
              </transition>
            </v-col>
          </v-row>
        </v-container>
      </v-main>
    </v-app>
  </div>
</template>
<script>
import Header from '@/components/Header.vue';

export default {
  components: {
    Header,
  },
};
</script>
<style lang="scss" >
 //@import "@/assets/Scss/_main.scss";
*{
    margin: 0px;
    padding: 0px;
}
</style>

