<template>
  <div>
    <v-app>
      <v-app-bar
        style="
          background-color: #0000003b !important;
          backdrop-filter: blur(10px);
          position: fixed;
          z-index: 99 !important;
        "
      >
        <v-container fluid style="padding: 50px 130px 50px">
          <div
     
      class="menu_icon"
      style="
        position: fixed;
        display: flex;
        top: 21px;
        align-items: 
        center;
        left: 115px;
        z-index: 9999999999;
        transition: opacity 0.3s ease;
      "
    >
    <v-img
        class="logo"
        @click="menuFunction()"
        @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave"
                style="width: 40% "
                :src="require(`../assets/menus.png`)"
              ></v-img>
      <span
        @mouseenter="handleMouseEnter"
        @mouseleave="handleMouseLeave"
        style="font-size: 14px; color: #fff; padding-left: 12px"
        >{{ menuText }}</span
      >
    </div>
          <v-img
            width="50"
            style="margin: auto"
            :src="require(`../assets/logoone-light.png`)"
          ></v-img>
          <v-spacer></v-spacer>
        </v-container>
      </v-app-bar>

      <v-navigation-drawer
        style="
        position: fixed !important;
          z-index: 9999 !important; 
          background-color: rgb(0 0 0 / 65%) !important;
          backdrop-filter: blur(10px);
          width: 500px !important;
        "
        v-model="drawer"
        app
      >
      <v-list nav   >
          <v-subheader></v-subheader>
          <v-list-item :to="item.to" v-for="(item, i) in items" :key="i" link>
            <v-list-item-icon></v-list-item-icon>
            <v-list-item-content >
              <v-list-item-title
                style="
                display: flex;
                justify-content: center;
              
                  margin: 10px 0;
                color: white;
                  font-size: 16px;
                  font-weight: 800;
                  text-transform: uppercase;
                "
                >{{ item.title }}</v-list-item-title
              >
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    <v-main>
            <router-view></router-view>
          </v-main>
      <v-row>
        <v-col cols="12" md="12">
          <v-container fluid class="hero">
            <h2
              style="
                font-size: 56px;
                color: #fff;
                letter-spacing: 2px;
                font-weight: 400;
                font-family: Helvetica Neue, sans-serif;
              "
            >
              GALLERY
            </h2>
            <p
              style="
                font-size: 24px;
                color: #fff;
                letter-spacing: 2px;
                font-weight: 400;
                font-family: Helvetica Neue, sans-serif;
              "
            >
              A Room Of Artspeak
            </p>
            <div
              style="
                background: #111010e3;
                padding: 15px 20px;
                border-radius: 20px;
                display: flex;
              "
            >
              <div
                style="               
                  font-size: 14px;
                  text-transform: uppercase;
                  font-weight: 700;
                  letter-spacing: 0.05em;
                  line-height: 20px;
                  color: #999;
                "
              >
                <i class="fa-thin fa-house-chimney"></i>
              </div>

            
              <p
                style="
                  margin: 0;
                  padding: 0;
                  float: left;
                  font-family: Helvetica Neue, sans-serif;
                  font-size: 14px;
                  text-transform: uppercase;
                  font-weight: 700;
                  letter-spacing: 0.05em;
                  line-height: 20px;
                  color: #999;
                "
              >
                Gallery
              </p>
            </div>
          </v-container>
        </v-col>
        <v-col cols="12" md="12">
          <v-container fluid style="padding: 30px 60px ">
            <v-row>
              <v-col
              v-for="(item, i) in image_dataset"
                  :key="i"
                cols="12"
                md="4"
                sm="12"
                xs="12"
                style="
                  justify-content: center;
                  display: flex;
                  flex-wrap: wrap;
                  column-gap: 50px;
                  padding-bottom: 30px;
                "
              >
                <v-hover
                width=" 33.33333333%"
                  v-slot="{ isHovering, props }"
                  open-delay="200"
                  
                >

               
                    
                  <v-card
                    style="display: flex;position:relative; align-items: end;  flex-direction: column; "
                    class="rounded-md"
                    :class="{ 'on-hover': isHovering }"
                    :elevation="isHovering ? 16 : 2"
                   
                   
                    v-bind="props"
                  
                  >
                  <img
      :src="require(`../assets/${item.img}`)"
      style="transform: scale(1); transition: transform 0.5s ease-in-out;"
      :style="{ transform: isHovering ? 'scale(1.1)' : 'scale(1)' }"
      height="100%"
      width="100%"
    />
                    <v-card-title
                      style="
                      position:absolute;
                      bottom:0;
                      left: 0;
                      background: #726e6eba;
                        text-align: center;
                        height: 50px;

                        padding: 10px 10px;
                        width: 100%;
                      "
                      >
                      <h6 style="font-size: 18px;
    font-weight: 300;
    color: #ddd;"> {{ item.title }}</h6>
                      <p style="    color: #ddd;
    font-size: 16px;">{{ item.txt }}</p>
                      </v-card-title
                    >
                  </v-card>
                </v-hover>
              </v-col>
            </v-row>

           
          </v-container>
        </v-col>
      </v-row>
      <v-footer style="background-color: #000000">
        <v-container style="padding: 0px 0px 20px" fluid>
          <v-row style="padding: 0px 50px">
            <v-col
              cols="12"
              md="12"
              class="pa-0"
              style="text-align: center; padding-top: 40px !important"
            >
              <v-img
                width="150"
                style="margin: auto"
                :src="require(`../assets/logo-light.png`)"
              ></v-img>
              <h6
                style="
                  text-transform: uppercase;
                  margin-top: 10px;
                  font-size: 15px;
                  padding-bottom: 40px !important;
                  color: #fff;
                "
              >
                PHOTOGRAPHY
              </h6>
            </v-col>
            <v-col
              cols="12"
              class="pa-2"
              md="12"
              style="
                border-top: 1px solid #3b3b3b;
                border-bottom: 1px solid #3b3b3b;
                padding-top: 30px !important;
                padding-bottom: 30px !important;
                width: 100%;
                display: flex;
                align-items: center;
              "
            >
              <v-row>
                <v-col class="pa-2" cols="12" md="5">
                  <h6
                    style="
                      color: #fff;
                      font-size: 16px;
                      text-transform: uppercase;
                      margin-left: 3px;
                      margin-bottom: 10px;
                    "
                  >
                    gallery
                  </h6>
                  <h6
                    style="
                      color: #fff;
                      font-size: 16px;
                      text-transform: uppercase;
                      margin-left: 3px;
                      margin-bottom: 10px;
                    "
                  >
                    films
                  </h6>
                  <h6
                    style="
                      color: #fff;
                      font-size: 16px;
                      text-transform: uppercase;
                      margin-left: 3px;
                      margin-bottom: 10px;
                    "
                  >
                    contact
                  </h6>
                </v-col>
                <v-col
                  cols="12"
                  md="3"
                  class="py-2"
                  style="display: flex; padding-right: 75px"
                >
                  <v-img
                    width="5"
                    style="margin-right: 30px"
                    :src="require(`../assets/instagram.png`)"
                  ></v-img>
                  <v-img
                    width="5"
                    style="margin-right: 30px"
                    :src="require(`../assets/facebook.png`)"
                  ></v-img>
                  <v-img
                    style="margin-right: 30px"
                    width="5"
                    :src="require(`../assets/youtube.png`)"
                  ></v-img>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-footer>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "HelloWorld", 
  data: () => ({
    drawer: false,
    hideMenu: false,
    hideApp: false,
    hideMenu2: true,

    menuText: "Menu",
    selectedItem: null,
    items: [
      { title: "Home", icon: "", to: "/" },
      { title: "Gallery", icon: "", to: "gallery" },
      { title: "Films", icon: "", to: "films" },
      { title: "Contact", icon: "", to: "contact" },
    ],

    image_dataset: [
      {
        img: "01_AKUL_KAVYA.webp",
        title: "AKUL // KAVYA",
        txt:"Punjabi Wedding",
      },

      {
        img: "02-PRASHANTH_MANASA.webp",
        title: "PRASHANTH // MANASA",
        txt:"Brahmin Wedding",
      },
      {
        img: "03-JEI_GEETHANCHALI.webp",
        title: "JEI // GEETHANCHALI",
        txt:"Concept Shoot",
      },
      {
        img: "04-HENDRU_RENEE.webp",
        title: "HENDRY // RENEE",
        txt:"Christian Wedding",
      },
      {
        img: "05-DEEPAK_MATHI.webp",
        title: "DEEPAK // MATHI",
        txt:"Kongu Wedding",
      },
      {
        img: "06-PRITHIV_PRIYA.webp",
        title: "PRITHIV // PRIYA",
        txt:"Concept Shoot",
      },
      {
        img: "07-AKUL_KAVYA.webp",
        title: "AKUL // KAVYA",
        txt:"Punjabi Haldi",
      },
      {
        img: "08-SIBI_PRANAVI.webp",
        title: "SIBI // PRANAVI",
        txt:"Kongu Wedding",
      },
      {
        img: "09-KARTHICK_PAVITHRA.webp",
        title: "KARTHICK // PAVITHRA",
        txt:"KARTHICK // PAVITHRA",
      },
      {
        img: "10-BOOBALAN_ARUNA.webp",
        title: "BOOBALAN // ARUNA",
        txt:"Concept Shoot",
      },
      {
        img: "11-JONAS_LEDYYA.webp",
        title: "JONAS // LEDYYA",
        txt:"Christian Wedding",
      },
      {
        img: "12-AJAY_SANA.webp",
        title: "JONAS // LEDYYA",
        txt:"Christian Wedding",
      },
      {
        img: "13-MELVIN_HELEN.webp",
        title: "JONAS // LEDYYA",
        txt:"Christian Wedding",
      },
      {
        img: "14-KARTHICK_PAVITHRA.webp",
        title: "KARHICK // PAVITHRA",
        txt:"Recption",
      },
      {
        img: "15-PRAVIN_PAVITHRA.webp",
        title: "PRAVIN // PAVITHRA",
        txt:"Concept Shoot",
      },
      {
        img: "16-KAVYA_AKUL.webp",
        title: "KAVYA // AKUL",
        txt:"Brahmin Wedding",
      },
      {
        img: "17-BOOBALAN_ARUNA.webp",
        title: "BOOBALAN // ARUNA",
        txt:"Tamil Wedding",
      },
      {
        img: "18-RAM_NITHYA.webp",
        title: "RAM // NITHYA",
        txt:"Tamil Wedding",
      },
      {
        img: "19-ARUN_ARUNA.webp",
        title: "ARUN // ARUNA",
        txt:"Brahmin Wedding",
      },

    ],
  }),
  methods: {
    handleScroll() {
      if (window.scrollY > 20) {
        this.hideMenu = true;
        this.hideApp = true;
        this.hideMenu2 = false;
      } else {
        this.hideApp = false;
        this.hideMenu = false;
        this.hideMenu2 = true;
      }
    },
    menuFunction() {
      this.drawer = !this.drawer;
      this.updateMenuText();
    },
    updateMenuText() {
      if (this.drawer) {
        this.menuText = this.drawer ? "Menu" : "Close";
      } else {
        this.menuText = this.drawer ? "Open" : "Menu";
      }
    },
    handleMouseEnter() {
      if (this.drawer) {
        this.menuText = "Close";
      } else {
        this.menuText = "Open";
      }
    },
    handleMouseLeave() {
      if (this.drawer) {
        this.menuText = "Menu";
      } else {
        this.menuText = "Menu";
      }
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Quicksand:wght@300..700&display=swap");
</style>

<style>
* {

}
.common_btns {
  padding: 16px 40px;
  background-color: #cab08b;
  border-radius: 40px;

  text-transform: uppercase;
  font-weight: 600;
}


.v-window__controls {
  align-items: flex-start !important;
  padding-left: 175px !important;
  padding-right: 175px !important;
}
.hero {
  background: url("../assets/river.gif");
  background-size: cover;
  height: 80vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  /* display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center; */
  background-attachment: fixed;
}
@media only screen and (max-width: 768px) {
  .menu_icon {
    left: 20px  !important;
  }
}

</style>
