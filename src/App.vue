<template>
  <div class="q-pa-md">
    <q-carousel
      swipeable
      animated
      v-model="slide"
      :autoplay="autoplay"
      ref="carousel"
      infinite
    >
      <q-carousel-slide :name="1">
        <img src="/images/gambar 1.jpeg" />
      </q-carousel-slide>
      <q-carousel-slide :name="2">
        <img src="/images/gambar 2.jpeg" />
      </q-carousel-slide>
      <q-carousel-slide :name="3">
        <img src="/images/gambar 3.jpeg" />
      </q-carousel-slide>
      <q-carousel-slide :name="4">
        <img src="/images/gambar 4.jpeg" />
      </q-carousel-slide>

      <template v-slot:control>
        <q-carousel-control
          position="top-right"
          :offset="[18, 18]"
          class="text-white rounded-borders"
          style="background: rgba(0, 0, 0, .3); padding: 4px 8px;"
        >
          <q-toggle dense dark color="orange" v-model="autoplay" label="Auto Play" />
        </q-carousel-control>

        <q-carousel-control
          position="bottom-right"
          :offset="[18, 18]"
          class="q-gutter-xs"
        >
          <q-btn
            push round dense color="orange" text-color="black" icon="arrow_left"
            @click="$refs.carousel.previous()"
          />
          <q-btn
            push round dense color="orange" text-color="black" icon="arrow_right"
            @click="$refs.carousel.next()"
          />
        </q-carousel-control>
      </template>
    </q-carousel>
  </div>
  <div id="app">
    <header>
      <h1>Toko Sepatu</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#products">Products</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>
    
    <section id="home">
      <h2>Welcome to Toko Sepatu</h2>
      <p>Your one-stop shop for the latest and greatest in footwear.</p>
    </section>
    
    <section id="about">
      <h2>About Us</h2>
      <p>We offer a wide variety of shoes to fit any style and occasion.</p>
    </section>
    
    <section id="products">
      <h2>Our Products</h2>
      <div class="product-list">
        <div class="product" v-for="(product, index) in products" :key="index">
          <img :src="product.image" :alt="product.name">
          <h3>{{ product.name }}</h3>
          <p>{{ product.description }}</p>
          <p class="price">{{ product.price }}</p>
        </div>
      </div>
    </section>
    
    <section id="contact">
      <h2>Contact Us</h2>
      <p>Email: info@shahnawaaznabeeltegar.com</p>
      <p>Phone: +62 123-456-7890</p>
    </section>
    
    <div class="q-pa-md">
    <q-card class="my-card">
      <iframe width="560" height="315" src="https://www.youtube.com/embed/mzB1VGEGcSU?si=JNCyrZJ2kM5wUeNk" frameborder="0" allowfullscreen></iframe>


      <q-card-section>
        <div class="text-h6">Lucid Dream</div>
        <div class="text-subtitle2">by Juice WRLD</div>
      </q-card-section>

      <q-card-section class="q-pt-none">
        Terimakasih Telah Berbelanja di toko kami
      </q-card-section>
    </q-card>
  </div>

    <footer>
      <p>&copy; 2024 Shah Nawaaz Nabeel Tegar. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      slide: ref(1),
      autoplay: ref(false)
    }
  },
  data() {
    return {
      products: [
        {
          name: 'Sport Shoes',
          description: 'Comfortable and stylish sport shoes.',
          price: 'Rp 500.000',
          image: '/images/7 (1).jpeg'
        },
        {
          name: 'Casual Shoes',
          description: 'Perfect for everyday wear.',
          price: 'Rp 300.000',
          image: '/images/7 (2).jpeg'
        },
        {
          name: 'Formal Shoes',
          description: 'Elegant and classy formal shoes.',
          price: 'Rp 700.000',
          image: '/images/7 (3).jpeg'
        }
      ]
    };
  }
};
</script>

<style scoped>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  color: #333;
}

header {
  background: #f8f8f8;
  padding: 20px;
  border-bottom: 1px solid #ddd;
}

header h1 {
  margin: 0;
  font-size: 24px;
}

nav ul {
  list-style: none;
  padding: 0;
}

nav ul li {
  display: inline;
  margin: 0 10px;
}

nav ul li a {
  text-decoration: none;
  color: #333;
}

section {
  padding: 40px 20px;
  border-bottom: 1px solid #ddd;
}

.product-list {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.product {
  border: 1px solid #ddd;
  padding: 20px;
  margin: 10px;
  width: 200px;
  box-shadow: 2px 2px 8px rgba(0,0,0,0.1);
}

.product img {
  width: 100%;
  height: auto;
}

.product h3 {
  font-size: 18px;
  margin: 10px 0;
}

.product .price {
  color: #e91e63;
  font-weight: bold;
}

footer {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background-color: #333;
  color: #fff;
  padding: 20px 0;
}
</style>
