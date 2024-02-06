<template>
  <div class="q-pa-md">
    <q-carousel
      animated
      v-model="slide"
      navigation
      infinite
      :autoplay="autoplay"
      arrows
      transition-prev="slide-right"
      transition-next="slide-left"
      @mouseenter="autoplay = false"
      @mouseleave="autoplay = true"
    >
      <q-carousel-slide
        :name="1"
        img-src="https://atimg.sonyunara.com/files/attrangs/new_banner/1706669368_0.jpg"
      />
      <q-carousel-slide
        :name="2"
        img-src="https://atimg.sonyunara.com/files/attrangs/new_banner/1706691517_0.jpg"
      />
      <q-carousel-slide
        :name="3"
        img-src="https://atimg.sonyunara.com/files/attrangs/new_banner/1706520455_0.jpg"
      />
    </q-carousel>
  </div>
</template>
<script setup>
import { ref } from 'vue';
const slide = ref(1);
const autoplay = ref(true);
</script>
