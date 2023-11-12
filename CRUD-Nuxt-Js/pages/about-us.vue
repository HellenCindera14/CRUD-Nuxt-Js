<template>
  <div class="full-screen-image">
    <img
      src="https://luxurycoastal.co.uk/wp-content/uploads/2020/02/mike-austin-iRbFUal-qWU-unsplash-scaled.jpg"
      alt="Your Image Description"
    />
  </div>
  <div class="container">
    <div class="left"></div>
    <div class="judul">
      <h1>Tentang Kami</h1>

        <p class="text-justify-1">
          Jakarta, 7 Juli 2020 - PT Aku Sayang Kamu - menyambut baik adanya
          pembukaan akses pelabuhan dibeberapa wilayah di Indonesia. Setelah
          adanya pembatasan pelaksanaan kegiatan transportasi laut dan
          ditutupnya sejumlah pelabuhan di masa pandemi Covid-19, hingga saat
          ini (7/7) sudah terdapat 61 Pelabuhan yang membuka aksesnya baik untuk
          embarkasi dan debarkasi bagi penumpang serta 5 pelabuhan yang hanya
          melayani proses embarkasi.
        </p>
        <p class="text-justify-2">
          Direktur Aku Syanag Kamu (Persero), Helen Cindera
          menyampaikan bahwa setelah adanya pelonggaran perjalanan bagi
          penumpang,  mencatatkan sebanyak 14.685 pelanggan telah
          berpergian dengan kapal penumpang sejak Mei 2020 hingga 5 Juli 2020
          dan sebanyak 16.456 pelanggan yang berpergian dengan kapal perintis
          pada periode yang sama.
        </p>
        <p class="text-justify-3">
          Terdapat dua kapal yang akan beroperasi pada 10 Juli 2020, yakni KM
          Kelud dengan rute Tg. Priok - Kijang - Batam - Belawan (PP), serta KM
          Ciremai dengan rute Semarang - Tg. Priok - Surabaya - Makassar -
          BauBau - Sorong - Manokwari - Biak - Jayapura - Biak - Manokwari -
          Sorong - Namlea - BauBau - Makassar - Surabaya - Tg. Priok.
        </p>
      </div>
    </div>
  <div>
    <footer style="background-color: #87CEEB; color: white; text-align: center; padding: 40px 0;">
      <div style="width: 100%; max-width: 1200px; margin: 0 auto;">
        <p style="margin: 0;">&copy; 2023 Your Company. All rights reserved. by : @Helen Cindera.</p>
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
  text-align: justify;
}
.text-justify-2 {
  text-align: justify;
}
.text-justify-3 {
  text-align: justify;
}
.footer {
   background-color: #87CEEB; /* Warna biru muda */
  color: white; /* Warna teks untuk kontras dengan latar belakang */
  padding: 20px 0;
  text-align: center;
}


</style>
