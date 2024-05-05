<template>
    <div>
      <v-container>
        <v-row>
          <v-col v-for="(project, index) in projects" :key="index" cols="12" md="6" lg="4">
            <v-card @click="toggleImageCarousel(index)" class="card">
              <v-img :src="project.photos[0]" aspect-ratio="2"></v-img>
              <v-card-title>{{ project.name }}</v-card-title>
              <v-card-subtitle>

                <a :href="project.link" target="_blank">{{ project.description }}</a>
              </v-card-subtitle>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
  
      <!-- Image Carousel Modal -->
      <v-dialog v-model="showImageCarousel" width="70%">
        <v-carousel v-if="selectedProject" hide-delimiter-background>
          <v-carousel-item v-for="(photo, photoIndex) in selectedProject.photos" :key="photoIndex">
            <v-img :src="photo" aspect-ratio="2"></v-img>
          </v-carousel-item>
        </v-carousel>
      </v-dialog>
    </div>
  </template>
  
  <script>
  import order1 from '@/assets/order1.jpg';
  import order2 from '@/assets/order2.jpg';
  import order3 from '@/assets/order3.jpg';
  import order4 from '@/assets/order4.jpg';
  import order5 from '@/assets/order5.jpg';
  import order6 from '@/assets/order6.jpg';
  import clothes1 from '@/assets/clothes1.png';
  import clothes2 from '@/assets/clothes2.png';
  import clothes3 from '@/assets/clothes3.png';
  import clothes4 from '@/assets/clothes4.png';
  import clothes5 from '@/assets/clothes5.png';
  import clothes6 from '@/assets/clothes6.png';
  import clothes7 from '@/assets/clothes7.png';
  import card from '@/assets/card.png';
  
  export default {
    data() {
      return {
        projects: [
          {
            id: 1,
            name: 'Order Service',
            description: 'Team Project',
            photos: [order1, order2, order3, order4, order5, order6]
          },
          {
            id: 2,
            name: 'Clothes Shop',
            description: 'Link: https://tinyurl.com/2uafpx6t',
            link: 'https://tinyurl.com/2uafpx6t',
            photos: [clothes1, clothes2, clothes3, clothes4, clothes5, clothes6, clothes7]
          },
          {
            id: 3,
            name: 'Card Game',
            description: 'Link: https://tinyurl.com/4zr6fnx6 ',
            link: 'https://tinyurl.com/4zr6fnx6',
            photos: [card]
          },
        ],
        showImageCarousel: false,
        selectedProjectIndex: null
      };
    },
    computed: {
      selectedProject() {
        return this.selectedProjectIndex !== null ? this.projects[this.selectedProjectIndex] : null;
      }
    },
    methods: {
      toggleImageCarousel(index) {
        this.selectedProjectIndex = index;
        this.showImageCarousel = true;
      }
    }
  };
  </script>
<style scoped>
.card {
  margin-bottom: 10px;
}
  
