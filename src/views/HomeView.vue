<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      
      :style="{ opacity: drawer ? 0.5 : 1 }" 
          
    >
    <v-list dense nav>
      <v-subheader>REPORTS</v-subheader>
     
        <v-list-item
        :to="item.to"
          v-for="(item, i) in items"
          :key="i"
          link
        >
          <v-list-item-icon>
            <!-- <v-icon ></v-icon> -->
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
     
    </v-list>
    </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="menuFunction()" @mouseenter="handleMouseEnter" @mouseleave="handleMouseLeave"></v-app-bar-nav-icon>

      <v-app-bar-title>{{ menuText }}</v-app-bar-title>
    </v-app-bar>

    <v-main>
      <router-view> </router-view>
    </v-main>
  </v-app>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomeView',
  data: () => ({ 
    drawer: false,
    menuText: 'Menu',
    selectedItem: null,
    items: [
          { title: 'Home', icon: '', to: "/" },
          { title: 'About', icon: '' , to: "about" }
        ]
  }),
  methods: {
    menuFunction() {
      this.drawer = !this.drawer;
      this.updateMenuText();
    },
    updateMenuText() {
      if (this.drawer) {
        this.menuText = this.drawer ? 'Close' : 'Menu';
      } else {
        this.menuText = this.drawer ? 'Menu' : 'Open';
      }
    },
    handleMouseEnter() {
      if (this.drawer) {
        this.menuText = 'Close';
      } else {
        this.menuText = 'Open';
      }
    },
    handleMouseLeave() {
      if (this.drawer) {
        this.menuText = 'Menu';
      } else {
        this.menuText = 'Menu';
      }
    }
  },  
});
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap');

* {
  background-color: #f9f9f9;
  font-family: "Quicksand", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
}

</style>
