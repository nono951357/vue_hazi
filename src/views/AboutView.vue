<template>
  <div class="font-sans bg-background-color min-h-screen">


    <section class="text-center py-16 bg-white shadow-md">
      <h2 class="text-3xl font-semibold mb-4 text-green-600">Fenntartható Energia Megoldások</h2>
      <p class="text-gray-700 max-w-2xl mx-auto">
        Az EcoVision Solutions segít a vállalatoknak átállni a megújuló energiaforrásokra, miközben csökkenti a
        költségeket.
        Szakértő tanácsadóink személyre szabott stratégiákat nyújtanak a fenntartható növekedéshez és környezeti
        felelősségvállaláshoz.
      </p>
    </section>



    <section class="bg-gray-50 text-center py-16">
      <h2 class="text-3xl font-semibold mb-4 text-green-600">Hatásunk</h2>
      <p class="text-gray-700 mb-6 max-w-2xl mx-auto">
        Több mint 100 vállalatnak segítettünk 50%-kal csökkenteni a szénlábnyomát, miközben milliókat takarítottak meg
        az energiaköltségeken.
        Innovatív megoldásaink ötvözik a nap-, szél- és energiahatékonysági technológiákat.
      </p>

      <div class="relative max-w-4xl mx-auto">
        <!-- Carousel Container -->
        <div class="overflow-hidden relative">
          <div class="flex transition-transform duration-500 ease-in-out"
            :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
            <!-- Carousel Items -->
            <div v-for="(image, index) in images" :key="index" class="w-full flex-shrink-0">
              <div class="relative">
                <img :src="image.url" :alt="image.alt" class="w-full h-[400px] object-cover rounded-lg shadow-lg">
                <div class="absolute bottom-0 left-0 right-0 bg-black/50 text-white p-2 text-center rounded-b-lg">
                  {{ image.alt }}
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Navigation Buttons -->
        <button @click="prevSlide"
          class="absolute left-2 top-1/2 -translate-y-1/2 bg-white/80 p-2 rounded-full shadow-lg hover:bg-white">
          <span class="text-2xl">←</span>
        </button>
        <button @click="nextSlide"
          class="absolute right-2 top-1/2 -translate-y-1/2 bg-white/80 p-2 rounded-full shadow-lg hover:bg-white">
          <span class="text-2xl">→</span>
        </button>

        <!-- Dots Indicator -->
        <div class="absolute -bottom-8 w-full flex justify-center gap-2">
          <button v-for="(_, index) in images" :key="index" @click="currentSlide = index"
            :class="['w-3 h-3 rounded-full', currentSlide === index ? 'bg-green-600' : 'bg-gray-300']">
          </button>
        </div>
      </div>
    </section>



    <section class="py-16 bg-white shadow-md">
      <h2 class="text-center text-3xl font-semibold mb-8 text-green-600">Szolgáltatásaink</h2>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 px-4 sm:px-16">
        <div class="bg-white shadow-lg rounded-lg overflow-hidden transform transition duration-500 hover:scale-105">
          <div class="p-6">
            <h3 class="font-semibold mb-2 text-xl text-green-600">Energia Auditok</h3>
            <p class="text-gray-700">
              Az energiafogyasztási minták átfogó elemzése és a megújuló energia bevezetésével elérhető potenciális
              megtakarítások azonosítása.
            </p>
          </div>
        </div>
        <div class="bg-white shadow-lg rounded-lg overflow-hidden transform transition duration-500 hover:scale-105">
          <div class="p-6">
            <h3 class="font-semibold mb-2 text-xl text-green-600">Napenergia Megoldások</h3>
            <p class="text-gray-700">
              Szakértői útmutatás a napelemek telepítéséhez, karbantartásához és optimalizálásához a maximális
              energiahatékonyság és megtérülés érdekében.
            </p>
          </div>
        </div>
        <div class="bg-white shadow-lg rounded-lg overflow-hidden transform transition duration-500 hover:scale-105">
          <div class="p-6">
            <h3 class="font-semibold mb-2 text-xl text-green-600">Zöld Tanúsítványok</h3>
            <p class="text-gray-700">
              Támogatás a zöld épület tanúsítványok megszerzésében és fenntartható gyakorlatok bevezetésében
              szervezetében.
            </p>
          </div>
        </div>
      </div>
    </section>



    <section class="bg-gray-50 text-center py-16">
      <h2 class="text-3xl font-semibold mb-4 text-green-600">Készen áll a zöld átállásra?</h2>
      <p class="text-gray-700 mb-6 max-w-2xl mx-auto">
        Csatlakozzon a megújuló energia forradalomhoz, és kezdjen el spórolni az energiaköltségeken, miközben védi a
        környezetet.
      </p>
      <button class="bg-green-600 text-white px-6 py-3 rounded-md shadow-md hover:bg-green-700 transition duration-300">
        Ingyenes Konzultáció
      </button>
    </section>



  </div>
</template>

<script>
export default {
  data() {
    return {
      currentSlide: 0,
      timer: null,
      images: [
        { url: 'https://ecols.hu/storage/hero/ecologistic-solution-hero-4.jpg', alt: 'Napelem Telepítés' },
        { url: 'https://supairvision.com/images/builder/age-carousel-637f2b1fc45e52-46860030-2-64c1176f8ae469.28168044.webp', alt: 'Szélturbinák' },
        { url: 'https://epiteszforum.hu/uploads/images/2021/04/952_epiteszforum-energiahatekony-otthon-okos-dontesekkel-0-10-2021-04-07-151959.jpg', alt: 'Energiahatékony Épület' },
        { url: 'https://media.licdn.com/dms/image/D4D12AQG9EahNJsd15Q/article-cover_image-shrink_720_1280/0/1700018267059?e=2147483647&v=beta&t=oJf19XQKToshZKhSq2iD5um22Ur1JxyN8oUPoTHbnyA', alt: 'Zöld Technológia' },
        { url: 'https://igepa.hu/wp-content/uploads/fenntarthatosag.jpg', alt: 'Fenntartható Megoldások' },
      ]
    }
  },
  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.images.length
    },
    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + this.images.length) % this.images.length
    },
    startAutoTransition() {
      this.timer = setInterval(this.nextSlide, 7000)
    }
  },
  mounted() {
    this.startAutoTransition()
  },
  beforeUnmount() {
    if (this.timer) {
      clearInterval(this.timer)
    }
  }
}
</script>