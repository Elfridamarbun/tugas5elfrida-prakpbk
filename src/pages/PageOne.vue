<template>
    <q-page>
      <div class="q-pa-md">
        <h1>Page One</h1>
        <p>This is Page One.</p>
  
        <!-- Carousel -->
        <q-carousel v-model="slide" animated>
          <q-carousel-slide v-for="(image, index) in images" :key="index" :name="index.toString()">
            <img :src="image" style="width: 100%; height: 300px; object-fit: cover;">
          </q-carousel-slide>
        </q-carousel>
  
        <!-- Product Cards -->
        <div class="q-gutter-md q-mt-md row justify-around">
          <q-card v-for="(product, index) in products" :key="index" class="q-mb-md" style="width: 300px">
            <q-img :src="product.image" style="height: 200px; object-fit: cover;"></q-img>
            <q-card-section>
              <div class="text-h6">{{ product.name }}</div>
              <div class="text-subtitle1">{{ product.price }}</div>
            </q-card-section>
            <q-card-actions>
              <q-btn flat color="primary" label="Buy Now" />
            </q-card-actions>
          </q-card>
        </div>
      </div>
    </q-page>
  </template>
  
  <script>
  export default {
    name: 'PageOne',
    data() {
      return {
        slide: 0,
        images: [
          'https://source.unsplash.com/random/800x600?nature1',
          'https://source.unsplash.com/random/800x600?nature2',
          'https://source.unsplash.com/random/800x600?nature3',
        ],
        products: [
          { name: 'Product 1', price: '$10', image: 'https://source.unsplash.com/random/300x300?product1' },
          { name: 'Product 2', price: '$20', image: 'https://source.unsplash.com/random/300x300?product2' },
          { name: 'Product 3', price: '$30', image: 'https://source.unsplash.com/random/300x300?product3' },
        ],
      };
    },
  }
  </script>
  
  <style scoped>
  /* Add any additional CSS if needed */
  </style>