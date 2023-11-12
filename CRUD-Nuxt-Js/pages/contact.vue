<template>
  <div class="full-screen-image">
    <img
      src="https://i.ytimg.com/vi/F0MiZMSlRC0/maxresdefault.jpg"
      alt="Your Image Description"
    />
  </div>
  <div class="container">
    <div class="left"></div>
    <div class="judul">
      <h1>Jasa Logistik</h1>

      <p class="text-justify-1">
        Melayani pengangkutan paket barang, dry/refeer container, general cargo,
        kendaraan maupun penyewaan kapal angkutan komersial.
      </p>
      <p class="text-justify-2">
        Untuk menunjang bisnis jasa logistik, saat ini PT SAYANG KAMU memiliki
        26 kapal penumpang; 5 kapal barang Tol Laut; 1 kapal ternak; dan 7 kapal
        barang komersial. Temukan kebutuhan jasa logistik yang Anda cari, dan
        hubungi kami dengan mengisi formulir di bawah ini.
      </p>
      <h5>Angkutan Barang Komersial</h5>
      <h3>Red Pack</h3>
      <p class="text-justify-3">
        Pengiriman paket barang dengan kapal ASK hingga ke tangan penerima
        dengan batasan dimensi 100x50x50cm atau berat maksimal 120kg. Klik link
        disini, dll
      </p>
    </div>
  </div>
  <div>
    <footer
      style="
        background-color: #87ceeb;
        color: white;
        text-align: center;
        padding: 40px 0;
      "
    >
      <div style="width: 100%; max-width: 1200px; margin: 0 auto">
        <p style="margin: 0">
          &copy; 2023 Your Company. All rights reserved. by : @Helen Cindera.
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
useHead({
  title: "Home Page",
});
</script>

<style scoped>
.container {
  margin-top: -23%;
  width: 100%;
  height: 100%;
  display: flex;
}
.left {
  flex: 1;
}
.full-screen-image {
  width: 100%;
  height: 100vh; /* 100% viewport height */
  overflow: hidden; /* Optional: Hide overflow */
}

.full-screen-image img {
  width: 100%;
  height: 50%;
  object-fit: cover; /* Scale image to cover container */
}

.judul {
  flex: 3;
}
.judul h1 {
  margin-top: 3%;
  text-decoration: solid;
}
.img2 {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.img2 img {
  width: 100%;
  height: 50%;
  object-fit: cover; /* Scale image to cover container */
}

.text-justify-1 {
  font-size: 30px;
  text-align: justify;
}
.text-justify-2 {
  text-align: justify;
}
.text-justify-3 {
  text-align: justify;
}
.footer {
  background-color: #87ceeb; /* Warna biru muda */
  color: white; /* Warna teks untuk kontras dengan latar belakang */
  padding: 20px 0;
  text-align: center;
}
</style>
