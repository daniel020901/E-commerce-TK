<template>
  <div class="card shadow cart-product">
    <img
      :src="'assets/images/' + product.gambar"
      class="card-img-fluid p-2"
      alt="..."
    />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">Rp.{{ product.harga }}</p>
      <button class="btn btn-success">
        <b-icon-cart></b-icon-cart
        ><a
          href="https://app.sandbox.midtrans.com/payment-links/1714102023688"
          class="text-white no-underline"
          >Pesan</a
        >
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style>
</style>