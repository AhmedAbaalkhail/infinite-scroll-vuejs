<template>
  <div class="app">
    <div v-infinite-scroll="loadMore" infinite-scroll-disabled="busy" infinite-scroll-distance="limit">
    <v-container grid-list-xl>
      <v-layout wrap>
        <v-flex xs12 sm6 md4 v-for="photo in photos" :key="photo.id" mb-2>
        <v-card min-width="250px">
      <v-img :src="photo.url" aspect-ratio="1"></v-img>
          <v-card-title primary-title>
            <div>
              <h2>{{photo.title}}</h2>
            </div>
          </v-card-title>
          <v-card-actions class="justify-center">
            <Popup 
            v-bind:title="photo.title" 
            v-bind:albumId="photo.albumId"
            v-bind:id="photo.id"
            v-bind:thumbnailUrl="photo.thumbnailUrl"
            />
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
    </v-container>
  </div>
</div>
  
</template>

<script>
import axios from "axios";
import Popup from './Popup';

export default {
  components: {Popup},
  name: "Home",
  data() {
    return {
      photos: [],
      results: [],
      busy: false,
      limit: 9
    };
  },

  methods: {
   
    loadMore() {
      
      this.busy = true;   
      axios.get("https://jsonplaceholder.typicode.com/photos").then(res => {
        
        const append = res.data.slice(this.photos.length,this.photos.length + this.limit )
               
        this.photos = this.photos.concat(append);

      this.busy = false;
      })
    }
  },
  created() {
   this.loadMore();
  }
};
</script>

<style scoped>
</style>