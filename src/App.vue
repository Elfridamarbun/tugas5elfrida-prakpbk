<template>
  <q-layout view="hHh lpR fFf">
    <!-- Navbar -->
    <q-header elevated class="bg-primary text-white">
      <q-toolbar>
        <q-btn flat dense round icon="" aria-label="Menu" @click="drawer = !drawer"></q-btn>
        <q-toolbar-title>My Helmet</q-toolbar-title>
        <q-btn flat dense round icon="" aria-label="Cart"></q-btn>
      </q-toolbar>
    </q-header>

    <!-- Drawer -->
    <q-drawer v-model="drawer" show-if-above bordered>
      <q-list>
      
        <q-item clickable v-ripple>
          <q-item-section>Home</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Shop</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Contact</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Page Content -->
    <q-page-container style="background-image: url('https://th.bing.com/th/id/OIP.VQQi97rQK7gjBW-1Rjlf-QHaE7?w=290&h=192&c=7&r=0&o=5&pid=1.7');">
      <q-page>
        <div class="q-pa-md">
          <!-- Carousel -->
          <q-carousel>
            <q-carousel-slide
              v-for="(slide, index) in slides"
              :key="index"
              :img-src="slide.img"
              :caption="slide.caption"
            />
          </q-carousel>

          <!-- Product Cards -->
          <div class="q-gutter-md q-mt-md row justify-around">
            <q-card v-for="(product, index) in products" :key="index" class="q-mb-md" style="width: 300px">
              <q-img :src="product.image" style="height: 200px; object-fit: cover;"></q-img>
              <q-card-section>
                <div class="text-h6">{{ product.name }}</div>
                <div class="text-subtitle1">{{ product.price }}</div>
                <div class="text-caption">Price: {{ product.price }}</div> <!-- Added price -->
              </q-card-section>
              <q-card-actions>
                <q-btn flat color="primary" label="Buy Now" />
              </q-card-actions>
            </q-card>
          </div>
        </div>
      </q-page>
    </q-page-container>

    <!-- Footer -->
    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg" alt="Logo">
          </q-avatar>
          <div>by uteng</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      drawer: false,
      slides: [
        { img: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxyhUcJvWnhJnhgJqrOUQvRbAwt_O1WkOjj4fzrA5BhRoEC0e1nC3_hYEaWHtncogc17Q&usq', caption: 'Helm Shop' },
        { img: 'https://s4.bukalapak.com/img/47987418103/s-330-330/data.png.webp', caption: 'New Arrivals: Latest Helmet Models' },
        { img: '', caption: 'Protect Your Head with Our Helmets' },
        // Add more carousel slides if needed
      ],
      products: [
        { name: 'NHK GP-1000', price: '135.000', image: 'https://s4.bukalapak.com/bukalapak-kontenz-production/content_attachments/39444/original/biltwell_lanesplitter_helmet.jpg' },
        { name: 'KYT RC7', price: '400.000', image: 'https://s4.bukalapak.com/img/47987418103/s-330-330/data.png.webp' },
        { name: 'MDS Super Pro Supermoto', price: '450.000', image: 'https://s2.bukalapak.com/img/7656429983/s-330-330/Helm_MDS_Supermoto_Double_Visor__Hitam_Doff.png.webp' },
        { name: 'Helm Retro Cargloss CF Avorio Naiade', price: '250.000', image: 'https://s0.bukalapak.com/img/59953698103/s-330-330/data.png.webp' },
        { name: 'HELM EVOLUTION TRAVELING RED DOFF HALF FACE MODEL GM EVO PS04', price: '240.000', image: 'https://s2.bukalapak.com/img/23410402003/large/data.jpeg.webp' },
      ],
    };
  },
}
</script>

<style>
/* Add any additional CSS if needed */
</style>