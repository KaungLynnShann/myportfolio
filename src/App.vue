<template>
  <v-app>
    <v-container>
      <v-btn color="blue" @click="navigate('home')">Home</v-btn>
      <v-btn color="blue" @click="navigate('about')">About</v-btn>
      <v-btn color="blue" @click="navigate('contact')">Contact</v-btn>

      <v-img src="@/assets/kaung.jpg" alt="Profile" style="width: 200px; height: 200px; border-radius: 50%;
      margin-top: 50px;"></v-img> 

       <div class="social-icons">
      <v-btn icon @click="openLink('https://www.facebook.com/are.pu1?mibextid=9R9pXO')" 
      style="margin-right: 20px;">
        <v-icon style="color: rgb(48, 18, 239);font-size: 40px;">mdi-facebook</v-icon>
      </v-btn>

      <v-btn icon @click="openLink('https://www.reddit.com/u/blahblahbanyar?utm_medium=android_app&utm_source=share')" 
      style="margin-right:20px ;">
       <v-icon style="color:tomato;font-size: 40px;">mdi-reddit</v-icon>
      </v-btn>

      <v-btn icon @click="openLink('https://github.com/KaungLynnShann')"
       style="margin-right: 20px;">
        <v-icon style="color:black;font-size: 40px;">mdi-github</v-icon>
      </v-btn>

      <v-btn icon @click="openLink('https://Discord.com/users/750714070562373763')">
        <img src="@/assets/discord.png" alt="Discord Icon" style="width: 40px; height: 40px;
        border-radius: 50%;"> 
      </v-btn>

      </div>
      <div class="copyright">
        <p>&copy; 2023 Kaung Lynn Shann. All rights reserved.</p>
      </div>

      <!-- Display the selected component -->
      <component :is="currentComponent" />

    </v-container>
  </v-app>
</template>

<script>
import Home from './components/Home.vue';
import About from './components/About.vue';
import Contact from './components/Contact.vue';

export default {
  data() {
    return {
      currentComponent: 'Home',
    };
  },
  methods: {
    navigate(component) {
      this.currentComponent = component;
    },
    openLink(url) {
      window.open(url, '_blank');
    },
  },
  components: {
    Home,
    About,
    Contact,
  },
};
</script>
<style  scoped>
 .social-icons {
  position: fixed;
  bottom:100px;
  left: 18%;
  transform: translateX(-50%);
 }
 .copyright {
  text-align: center;
  margin-top: 18px;
  padding: 10px;
  background-color: #f0f0f0;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
}
</style>
