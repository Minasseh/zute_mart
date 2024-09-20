<template>
  <div class="home">
    <section class="hero is-medium is-dark mb-6">
      <div class="hero-body has-text-centered">
        <p class="title mb-6">
          <strong>Welcome to Zute Mart</strong>
        </p>
        <p class="subtitle">
          Where you can find Everything
        </p>
      </div>
    </section>

    <div class="columns is-multiline">
      <div class="column is-12">
        <h2 class="is-size-2 has-text-centered">Latest Products</h2>
      </div>

      <ProductBox
        v-for="product in latestProducts"
        v-bind:key="product.id"
        v-bind:product="product"/>
    </div>

    <div class="columns is-multiline">
      <div class="column is-6">
        <h2 class="is-size-2 has-text-centered">Our Vision</h2>
        <div class="column has-background-warning">
          <p class="has-text-justified">At <strong><em>Zute Mart</em></strong>, we aspire to become the world’s most trusted marketplace, where customers can shop for any product imaginable with confidence and ease. We envision a vibrant digital shopping environment where variety meets convenience, catering to every lifestyle and taste.</p>
          <p class="has-text-justified">Our mission is to simplify the online shopping experience by offering a diverse selection of high-quality products in one easy-to-navigate space. With <strong><em>Zute Mart</em></strong>, you can enjoy a seamless shopping journey backed by advanced technology, a user-friendly interface, and customer-centric services.</p>
        </div>
      </div>

      <div class="column is-6">
        <h2 class="is-size-2 has-text-centered">Our Mission</h2>
        <div class="column has-background-warning">
          <p class="has-text-justified"><strong><h3>We are dedicated to offering</h3></strong></p>
          <hr>
          <ul class="has-text-centered has-text-justified">
            <li><strong>Extensive Product Selection:</strong> Zute Mart is your destination for a wide range of products across multiple categories.</li>
            <li><strong>Quality at Every Price Point:</strong> We work with top-tier suppliers and brands to bring you quality products at competitive prices, ensuring you get the best deals without compromising on value.</li>
            <li><strong>Customer First Approach:</strong> Your satisfaction is at the core of what we do. From fast shipping to flexible payment options and an easy returns process, we’re committed to making sure your experience with us is smooth and enjoyable.</li>
            <li><strong>Secure Shopping:</strong> Zute Mart uses advanced encryption and security protocols to protect your data. You can shop with peace of mind, knowing your information is safe.</li>
            <li><strong>Sustainability Matters:</strong> We care about the environment and work with suppliers that adhere to sustainable and eco-friendly practices.</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="column is-12">
      <h2 class="is-size-2 has-text-centered">Testimony</h2>
      <hr>
      <div class="column">
        <div class="box">
          
          <article class="media">
            <figure class="media-left">
              <p class="image is-64x64">
                <img src="https://www.pexels.com/photo/photo-of-man-wearing-denim-jacket-2691608/" />
              </p>
            </figure>
            <div class="media-content">
              <div class="content">
                <p>
                  <strong>John Doe</strong> <small>@johndoe</small> <small>1hr</small>
                  <br />
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare
                  magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa
                  sem. Etiam finibus odio quis feugiat facilisis.
                </p>
              </div>
              <nav class="level is-mobile">
                <div class="level-left">
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-reply"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-retweet"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-heart"></i></span>
                  </a>
                </div>
              </nav>
            </div>
            <div class="media-right">
              <button class="delete"></button>
            </div>
          </article>
        
        </div>
      </div>
      <div class="column">
        <div class="box">
          
          <article class="media">
            <figure class="media-left">
              <p class="image is-64x64">
                <img src="https://bulma.io/assets/images/placeholders/128x128.png" />
              </p>
            </figure>
            <div class="media-content">
              <div class="content">
                <p>
                  <strong>John Smith</strong> <small>@johnsmith</small> <small>31m</small>
                  <br />
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare
                  magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa
                  sem. Etiam finibus odio quis feugiat facilisis.
                </p>
              </div>
              <nav class="level is-mobile">
                <div class="level-left">
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-reply"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-retweet"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-heart"></i></span>
                  </a>
                </div>
              </nav>
            </div>
            <div class="media-right">
              <button class="delete"></button>
            </div>
          </article>

        </div>
      </div>
      <div class="column">
        <div class="box">
          
          <article class="media">
            <figure class="media-left">
              <p class="image is-64x64">
                <img src="https://bulma.io/assets/images/placeholders/128x128.png" />
              </p>
            </figure>
            <div class="media-content">
              <div class="content">
                <p>
                  <strong>John Smith</strong> <small>@johnsmith</small> <small>31m</small>
                  <br />
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ornare
                  magna eros, eu pellentesque tortor vestibulum ut. Maecenas non massa
                  sem. Etiam finibus odio quis feugiat facilisis.
                </p>
              </div>
              <nav class="level is-mobile">
                <div class="level-left">
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-reply"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-retweet"></i></span>
                  </a>
                  <a class="level-item">
                    <span class="icon is-small"><i class="fas fa-heart"></i></span>
                  </a>
                </div>
              </nav>
            </div>
            <div class="media-right">
              <button class="delete"></button>
            </div>
          </article>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import ProductBox from '@/components/ProductBox'

export default {
  name: 'HomeView',
  data() {
    return {
      latestProducts: []
    }
  },
  components: {
    ProductBox
  },
  mounted() {
    this.getLatestProducts()

    document.title = 'Home | Zute Mart'
  },
  methods: {
    async getLatestProducts() {
      this.$store.commit('setIsLoading', true)
      
      await axios
        .get('api/v1/latest-products/')
        .then(response => {
          this.latestProducts = response.data
        })
        .catch(error => {
          console.log(error)
        })

        this.$store.commit('setIsLoading', false)
    }
  }
}
</script>