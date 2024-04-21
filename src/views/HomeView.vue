<template>
  <div>
    
    <div
      class="menu_icon"
      style="
        position: fixed;
        display: flex;
        left: 115px;
        z-index: 9999999999 !important;
        transition: opacity 0.3s ease;
      "
       :style=" {top: menu_margin,
       }"
    >
      <!-- <i
        style="font-size: 18px; color: #fff; cursor: pointer"
       
       
      ></i> -->
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
    <div
    class="header_icon"
    v-show="!hideMenu"
     style="
  display: flex;
  justify-content: center;
        position: absolute !important;
        top: 0px !important ;
        z-index: 999999 !important;
        width: 100% !important;
        height:  120px ;
        
        ">
      <div style="border-bottom: 1px solid #fff !important; width: 80% !important;display: flex;
  justify-content: center; align-items: center;">
        <v-img
        class="logo"
                style="height: 20% "
                :src="require(`../assets/logo-light.png`)"
              ></v-img>

      </div>
    </div>

    <div
    v-show="!hideMenu2"
    class="header_icon"
     style="
  display: flex;
  justify-content: center;
        position: absolute !important;
        top: 0px !important ;
        z-index: 99999998 !important;
        width: 100% !important;
        height:  120px ;
        
        ">
      <div style="border-bottom: 1px solid #fff !important; width: 80% !important;display: flex;
  justify-content: center; align-items: center;">
        <v-img
                style="height: 20% "
                :src="require(`../assets/logo-light.png`)"
              ></v-img>

      </div>
    </div>
    <v-app>
      <v-app-bar
      
      v-if="hideApp"
        style="background-color: #0000003b !important; backdrop-filter: blur(10px);position: fixed"
      >
        <v-container fluid style="padding: 50px 130px 50px">
          <v-img
                width="40"
                style="margin: auto"
                :src="require(`../assets/logoone-light.png`)"
              ></v-img>
          <v-spacer></v-spacer>
        </v-container>
      </v-app-bar>
     
      <v-navigation-drawer
        style="
          z-index: 999999 !important;
         position: fixed;
         height: 100% !important;
          background-color: rgb(0 0 0 / 65%) !important;
          backdrop-filter: blur(10px);
          top: 0px !important;
          width: 500px !important;
           
        "
        v-model="drawer"
        app
      >
      <v-list nav  style="
    margin-top: 100px;" >
          <v-subheader ></v-subheader>
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

      <v-row>
        <v-col cols="12" md="12">
          <v-carousel
            height="100%"
            width="100%"
            :show-arrows="false"
            cycle
            hide-delimiters
          >
            <v-carousel-item v-for="(slide, i) in home_slides" :key="i">
              <v-sheet height="100%">
                <div class="d-flex fill-height justify-center align-center">
                  <v-img :src="require(`../assets/${slide.image}`)" />
                </div>
              </v-sheet>
            </v-carousel-item>
          </v-carousel>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="12">
          <v-container  class="container_padding" style="padding: 50px">
        <v-row>
          <v-col cols="12" md="12" class="text-center">
            <h2
              style="
                line-height: 1.6;
                padding-bottom: 30px;
                font-size: 35px;
                letter-spacing: 2px;
              "
            >
              WHO WE ARE
            </h2>
          </v-col>
          <v-col cols="12" md="12" class="text-center">
            <p style="color: #0009; line-height: 1.6; font-size: 15px">
              Founded in 2016, Art View is dedicated and passionate about
              documenting the wedding events and bringing out the soul of the
              wedding moment’s. The art of wedding photography itself is about
              capturing the emotions unfolding during the D-day. Our crew tells
              stories in a winsome manner with all the beautiful elements
              included. The extravaganza in the flamboyant nuptials makes our
              camera capture elegant pictures that will engrave in your heart
              forever. It would be a perpetual emotional memories which can
              bring back the Day alive with the same emotion even after years
              and can be shown to your future generations. Irrespective of
              borders, Art View covers affairs in Scotland, UK and other parts
              of the globe. No matter where your wedding destination is, we will
              exemplify your story of union which will remain a jaw-dropping
              one, even after years.!
            </p>
          </v-col>
          <v-col
            cols="12"
            md="12"
            class="text-center contact"
            style="padding-top: 100px"
          >
            <h2
              style="
                line-height: 1.6;
                padding-bottom: 30px;
                font-size: 35px;
                letter-spacing: 2px;
              "
            >
              CONTACT US
            </h2>
            <v-btn class="common_btns" size="x-large">Request Qoute</v-btn>
          </v-col>

          <v-col
            cols="12"
            md="12"
            class="text-center contact"
            style="padding-top: 100px; "
          >
            <v-row style="justify-content: center">
              <v-col
                cols="12"
                              md="4"
              
                
                style="
                  justify-content: center;
                  display: flex;
                  column-gap: 50px;
                  padding-bottom: 30px;
                "
                 v-for="(item, i) in image_dataset"
                  :key="i"
              >
                <v-hover
                 
                  v-slot="{ isHovering, props }"
                  open-delay="200"
                >
                  <v-card
                    class="rounded-xl"
                    :class="{ 'on-hover': isHovering }"
                    :elevation="isHovering ? 16 : 2"
                    height="350"
                    width="240"
                    v-bind="props"
                    :image="require(`../assets/${item.img}`)"
                  >
                  </v-card>
                </v-hover>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
        </v-col>
      </v-row>
   
      <v-row>
        <v-col cols="12" md="12" class="text-center">
          <v-btn class="common_btns" size="x-large" style="letter-spacing: 2px"
            >View Gallery</v-btn
          >
        </v-col>

        <v-col cols="12" md="12" class="text-center">
          <video
            style="object-fit: cover; width: 100%; height: 100%"
            data-autoplay=""
            autoplay=""
            muted=""
            loop=""
            playsinline=""
            preload="metadata"
          >
            <source type="video/webm" :src="videoSrc" />
          </video>
        </v-col>
      </v-row>
      <v-container class="container_padding" style="padding: 50px">
        <v-row>
          <v-col cols="12" md="12" sm="12" class="contact" style="padding-top: 100px">
            <v-row>
              <v-col cols="12" md="12" class="text-center">
                <h2
                  style="
                    line-height: 1.6;
                    padding-bottom: 30px;
                    font-size: 35px;
                    letter-spacing: 2px;
                  "
                >
                  MEET THE PILLARS
                </h2>
              </v-col>
              <v-col
                cols="12"
                lg="12"
                md="12"
                sm="12"
                xs="12"
                style="
                  justify-content: center;
                  display: flex;
                  flex-wrap: wrap;
                  column-gap: 50px;
                "
              >
                <v-hover
                  v-for="(item, i) in persons"
                  :key="i"
                  v-slot="{ isHovering, props }"
                  open-delay="200"
                >
                  <div>
                    <v-card
                      class="rounded-xl"
                      :class="{ 'on-hover': isHovering }"
                      :elevation="isHovering ? 16 : 2"
                      height="350"
                      width="240"
                      v-bind="props"
                      :image="require(`../assets/${item.img}`)"
                    >
                    </v-card>
                    <h4
                      style="
                        padding-top: 20px;
                        font-weight: 800;
                        font-size: 16px;
                        text-align: center;
                        letter-spacing: 2px;
                      "
                    >
                      {{ item.title }}
                    </h4>
                  </div>
                </v-hover>
              </v-col>
            </v-row>
          </v-col>
          <v-divider class="divider_class" style="margin-top: 100px"></v-divider>
          <v-col cols="12" md="12">
            <section>
              <v-row>
                <v-col
                  style="margin-top: 30px"
                  cols="12"
                  md="12"
                  class="text-center"
                >
                  <h2
                    style="
                      line-height: 1.6;
                      padding-bottom: 30px;
                      font-size: 35px;
                      letter-spacing: 2px;
                    "
                  >
                    CLIENT TESTIMONIAL’s
                  </h2>
                </v-col>
                <v-col cols="12" md="12">
                  <v-carousel class="carousel_h" height="150" cycle hide-delimiters>
                    <template v-slot:prev="{ props }">
                      <v-img
                      class="arrow_img1"
                      height="25"
                      @click="props.onClick"
                :src="require(`../assets/left.png`)"
              ></v-img>
                    </template>
                    
                    <template v-slot:next="{ props }">
                      <v-img
                      class="arrow_img2"
                      height="25"
                      @click="props.onClick"
                :src="require(`../assets/right.png`)"
              ></v-img>
                    </template>
                    <v-carousel-item v-for="(item, i) in slide_txt" :key="i">
                      <v-sheet
                        height="100%"
                        style="
                          display: flex;
                          align-items: flex-start;
                          justify-content: center !important;
                        "
                      >
                        <div style="max-width: 646px;  display: flex;
                        flex-direction: column;
                         align-items:  center;">
                          <p style="text-align: center; color: #0009; line-height: 1.6; font-size: 15px;">{{ item.txt }}</p>
                          <div
                          class="star"
                            style="
                            width:25%;
                              display: flex;
                              justify-content: center;
                              align-items: center; padding: 20px
                            "
                          >
                            <v-img
                            
                              height="15"
                              style="border-radius: 50%"
                              :src="require(`../assets/star.png`)"
                            ></v-img>
                            <v-img
                              height="15"
                              style="border-radius: 50%"
                              :src="require(`../assets/star.png`)"
                            ></v-img>
                            <v-img
                              height="15"
                              style="border-radius: 50%"
                              :src="require(`../assets/star.png`)"
                            ></v-img>
                            <v-img
                              height="15"
                              style="border-radius: 50%"
                              :src="require(`../assets/star.png`)"
                            ></v-img>
                            <v-img
                              height="15"
                              style="border-radius: 50%"
                              :src="require(`../assets/star.png`)"
                            ></v-img>
                           
                          </div>
                          <h6 style="text-align: center; font-size: 16px; font-weight: 500;line-height: 1.3; letter-spacing: 2px">{{ item.name }}</h6>
                        </div>
                      </v-sheet>
                    </v-carousel-item>
                  </v-carousel>
                </v-col>
              </v-row>
            </section>
          </v-col>
        </v-row>

        <v-main>
          <router-view></router-view>
        </v-main>
      </v-container>
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
                  font-weight: 500;
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
  created() {

    this.checkScreenSize();

    window.addEventListener('resize', this.checkScreenSize);
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  destroyed() {
    // Remove event listener on component destruction
    window.removeEventListener('resize', this.checkScreenSize);
  },
  data: () => ({
    drawer: false,
    menu_margin: "50px",
    isSmallScreen: false, 
    hideMenu: false,
    hideApp: false,
    hideMenu2: true,
    slides: [
      { image: "section1.webp" },
      { image: "section2.png" },
      { image: "section3.png" },
    ],
    home_slides: [
      { image: "slider1.webp" },
      { image: "slider2.webp" },
      { image: "slider3.webp" },
      { image: "slider4.webp" },
      { image: "slider7.webp" },
      { image: "slider8.webp" },
    ],

    slide_txt: [
      {
        name: "-Steve Jobs",
        txt: "“ We’ve gotten the nicest couple shots yesterday after nearly 5 years of shrey and i taking photos together - and that’s all because of the magic that you brought “",
      },

      {
        name: "-Walt Disney",
        txt: "“ We’ve gotten the nicest couple shots yesterday after nearly 5 years of shrey and i taking photos together - and that’s all because of the magic that you brought “",
      },
      {
        name: "-Nelson Mandela",
        txt: '"We’ve gotten the nicest couple shots yesterday after nearly 5 years of Shrey and I taking photos together - and that’s all because of the magic that you brought"',
      },
    ],
    menuText: "Menu",
    selectedItem: null,
    items: [
      { title: "Home", icon: "", to: "/" },
      { title: "Gallery", icon: "", to: "gallery" },
      { title: "Films", icon: "", to: "films" },
      { title: "Contact", icon: "", to: "contact" },
    ],
    textItems: ["Item 1", "Item 2", "Item 3", "Item 4", "Item 5", "Item 6"],
    videoSrc: require(`../assets/video.mp4`),
    image_dataset: [
      {
        img: "section1.webp",
      },

      {
        img: "section2.png",
      },
      {
        img: "section3.png",
      },
    ],
    persons: [
      {
        img: "team2.png",
        title: "NARESH",
      },

      {
        img: "team-1.png",
        title: "RANJITH SIVA SHANKAR",
      },
    ],
  }),
  methods: {
    handleScroll() {
      if (window.scrollY > 50) {
        this.hideMenu = true;
        this.hideApp = true;
        this.hideMenu2 = false;
        this.menu_margin = "25px";
      } else {
        this.hideApp = false;
        this.hideMenu = false;
        this.hideMenu2 = true;
        this.menu_margin = "50px";
      }
    },
    checkScreenSize() {
      // Check if screen width is smaller than a threshold (e.g., 600px)
      this.isSmallScreen = window.innerWidth < 600;
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

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Quicksand:wght@300..700&display=swap");
</style>

<style  scoped>
* {
  /* background-color: #f9f9f9; */
  font-family: "Quicksand", sans-serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
}
.common_btns {
  padding: 16px 40px;
  background-color: #cab08b;
  border-radius: 40px;

  text-transform: uppercase;
  font-weight: 600;
}

.my-selector {
  font-size: 16px;
}
.arrow_img1{
  position: relative;
  left: -110px !important;
}
.arrow_img2{
  position: relative;
  right: -110px !important;
}
.v-window__controls {
  align-items: flex-start !important;
  padding-left: 175px !important;
  padding-right: 175px !important;
}
@media only screen and (max-width: 768px) {
  .menu_icon {
    left: 20px  !important;
    top: 16px !important;
  }
  .header_icon {
    height: 60px  !important;
   
  }
  .logo{
    height: 20px  !important; 
  }
  .slide_icon{
    display: none  !important; 
  }
  .container_padding{
    padding: 20px !important;
  }
  h2,h4{
    padding-bottom: 10px !important;
  }
  .contact{
    padding-top: 10px !important;
 
  }
  .divider_class{
    margin-top: 10px !important;
  
  }
  .carousel_h{
    height: 200px !important;
  }
  .star{
    width: 40% !important;
  }
}

</style>
