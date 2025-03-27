<template>
    <div id="profile" class="grid sm:grid-cols-3 bg-gray-100 gap-1">
      <div v-for="item in slides" :key="item.title" class="px-12 py-12 sm:py-16 sm:p-6 divide-y-2 divide-gray-200 bg-white group">
        <div class="flex gap-4 md:gap-6">
          <div
            class="flex h-16 w-16 shrink-0 items-center justify-center rounded-lg group-hover:bg-blue-700 group-hover:text-white group-hover:shadow-lg md:h-14 md:w-14 md:rounded-xl">
            <Icon :name="item.description" class="w-12 h-12" />
          </div>
          <div>
            <h3 class="mt-0 sm:mt-0 mb-0 pr-8 sm:pr-0 group-hover:text-blue-700">{{ item.title }}</h3>
          </div>
        </div>
      </div>
    </div>
    <div data-aos="fade-right" class="grid sm:grid-cols-2">
      <div class="bg-[url(/kairos-2.jpg)] sm:h-full h-[600px] bg-cover bg-center grid content-end justify-end p-5">
        <div class="w-max bg-blue-700 text-white p-10">
          <h2 class="mb-2 text-5xl md:text-6xl text-center">10+</h2>
          <p class="-mt-2 font-bold text-sm text-center">TAHUN<br />BERKARYA</p>
        </div>
      </div>
      <div data-aos="fade-left" class="grid content-center sm:pr-24 py-12 sm:px-24 px-10 sm:pb-24">
        <span class="badgebiru w-max mb-2">about us</span>
        <h2 class=" uppercase">
          Selalu Aman bersama<br />
          <span class="text-blue-700">LAWAMENA</span>
        </h2>
        <p class="text-left">
          PT Kairos Mena Haulala atau lebih dikenal sebagai (“Lawamena”) merupakan
          perusahaan penyedia keamanan professional.
          <br /><br />
          Lawamena berkomitmen memberikan solusi keamanan yang andal dan
          terpercaya, melindungi serta menciptakan rasa aman di setiap anda.
          <br /><br />
          Tak hanya itu, Lawamena juga memiliki izin usaha konsultasi management
          di bidang Jasa Perizinan, sehingga dapat membantu mengembangkan bisnis
          anda ke langkah berikutnya.
        </p>
      </div>
    </div>
    <div data-aos="fade-right" class="grid sm:grid-cols-2">
      <div class="grid content-center bg-white sm:pr-24 sm:py-24 py-12 sm:px-24 px-10">
        <h4 class="mb-0 text-blue-700">Visi</h4>
        <p class="max-w-xl py-4 mb-4 leading-tight text-left">
          Menjadi penyedia jasa keamanan terpercaya yang memberikan rasa aman dan
          melindungi dari segala jenis tindak kejahatan.
        </p>
        <hr class="border-blue-700" />
        <h4 class="my-4 text-blue-700">Misi</h4>
        <ul class="list-outside">
          <li class="max-w-xl leading-tight text-left mb-5">
            Menyediakan layanan keamanan yang andal yang sesuai dengan kebutuhan
          </li>
          <li class="max-w-xl leading-tight text-left mb-5">
            Menyediakan tenaga keamanan yang tangguh, responsif, dan professional
          </li>
          <li class="max-w-xl leading-tight text-left">
            Memberikan layanan jasa perizinan yang tepat dan cepat.
          </li>
        </ul>
      </div>
      <div data-aos="fade-left" class="bg-[url(/kairos-3.jpg)] sm:h-full h-[600px] bg-cover bg-center grid content-center p-12"></div>
    </div>
  </template>
  
  <script setup>
  const slides = ref([
    {
      title: "LAYANAN KEAMANAN SESUAI KEBUTUHAN",
      description: "solar:lock-keyhole-minimalistic-unlocked-bold-duotone"
    },
    {
      title: "KERAHASIAN SUDAH PASTI TERJAMIN",
      description:
        "solar:user-block-bold-duotone"
    },
    {
      title: "PROFESIONAL, BERSERTIFIKAT DAN BERPENGALAMAN",
      description:
        "solar:heart-unlock-bold-duotone"
    },
  ]);
  const currentSlide = ref(0);
  let slideInterval;
  
  const nextSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % slides.value.length;
  };
  
  const prevSlide = () => {
    currentSlide.value =
      (currentSlide.value - 1 + slides.value.length) % slides.value.length;
  };
  
  const pauseSlider = () => {
    clearInterval(slideInterval);
  };
  
  const resumeSlider = () => {
    slideInterval = setInterval(nextSlide, 5000);
  };
  
  onMounted(() => {
    slideInterval = setInterval(nextSlide, 5000); // Transisi otomatis setiap 5 detik
  });
  
  onBeforeUnmount(() => {
    clearInterval(slideInterval);
  });
  </script>
  
  <style scoped>
  /* Untuk memastikan transisi fade */
  .opacity-0 {
    opacity: 0;
  }
  
  .opacity-100 {
    opacity: 1;
  }
  </style>
  