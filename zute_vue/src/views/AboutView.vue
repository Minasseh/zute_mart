<template>
  <div class="about">
    <div class="columns is-multiline">
      <div class="column is-12 has-text-centered">
        <h1 class="title">About Us</h1>
        <div class="column is-half is-offset-one-quarter">
          <p class="has-text-justified">Welcome to <strong><em>Zute Mart</em></strong>, your go-to online marketplace where you can find everything under the sun! We’re a one-stop e-commerce platform designed to meet all your shopping needs, from daily essentials to premium products. Whether you’re looking for the latest electronics, stylish fashion, home décor, groceries, or that perfect gift, <strong><em>Zute Mart</em></strong> has it all.</p>
        </div>
      </div>
      <hr>
      <div class="column is-12 has-text-centered">
        <h1 class="title">Our Vision</h1>
        <div class="column is-half is-offset-one-quarter">
          <p class="has-text-justified">At <strong><em>Zute Mart</em></strong>, we aspire to become the world’s most trusted marketplace, where customers can shop for any product imaginable with confidence and ease. We envision a vibrant digital shopping environment where variety meets convenience, catering to every lifestyle and taste.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Success',
    mounted() {
        document.title = 'About | Zute Mart'
    },
}
</script>
