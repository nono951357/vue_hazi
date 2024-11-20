<template>
    <!-- Hero Section -->
    <section class="bg-white py-16">
      <div class="container mx-auto px-4 text-center">
        <h1 class="text-4xl font-bold text-green-600 mb-6">Üdvözöljük az EcoVision Solutions-nél</h1>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">Vezető szerepben a fenntartható energiamegoldások terén</p>
      </div>
    </section>
  
    <!-- Meet Our Team -->
    <section class="bg-gray-50 py-16">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl font-bold text-center text-green-600 mb-12">Csapatunk</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="member in team" :key="member.name" class="bg-white rounded-lg shadow-lg p-6 text-center">
            <img :src="member.image" :alt="member.name" class="w-32 h-32 rounded-full mx-auto mb-4 object-cover">
            <h3 class="text-xl font-semibold mb-2">{{ member.name }}</h3>
            <p class="text-gray-600">{{ member.role }}</p>
          </div>
        </div>
      </div>
    </section>
  
    <!-- Features -->
    <section class="bg-white py-16">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl font-bold text-center text-green-600 mb-12">Szolgáltatásaink</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div v-for="feature in features" :key="feature.title" class="text-center">
            <div class="bg-green-100 w-16 h-16 rounded-full flex items-center justify-center mx-auto mb-4">
              <span class="text-2xl text-green-600">{{ feature.icon }}</span>
            </div>
            <h3 class="text-xl font-semibold mb-2">{{ feature.title }}</h3>
            <p class="text-gray-600">{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>
  
    <!-- Testimonials -->
    <section class="bg-gray-50 py-16">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl font-bold text-center text-green-600 mb-12">Ügyfeleink Mondták</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div v-for="testimonial in testimonials" :key="testimonial.name" class="bg-white p-6 rounded-lg shadow-lg">
            <p class="text-gray-600 mb-4">"{{ testimonial.quote }}"</p>
            <div class="font-semibold">{{ testimonial.name }}</div>
            <div class="text-sm text-gray-500">{{ testimonial.company }}</div>
          </div>
        </div>
      </div>
    </section>
  
    <!-- Get in Touch -->
    <section class="bg-white py-16">
      <div class="container mx-auto px-4">
        <h2 class="text-3xl font-bold text-center text-green-600 mb-12">Kapcsolat</h2>
        <div class="max-w-lg mx-auto">
          <form @submit.prevent="submitForm" class="space-y-6">
            <div>
              <label class="block text-gray-700 mb-2">Név</label>
              <input type="text" v-model="form.name" class="w-full p-3 border rounded-lg bg-white">
            </div>
            <div>
              <label class="block text-gray-700 mb-2">Email cím</label>
              <input type="email" v-model="form.email" class="w-full p-3 border rounded-lg bg-white">
            </div>
            <div>
              <label class="block text-gray-700 mb-2">Üzenet</label>
              <textarea v-model="form.message" rows="4" class="w-full p-3 border rounded-lg bg-white"></textarea>
            </div>
            <button type="submit" class="w-full bg-green-600 text-white py-3 rounded-lg hover:bg-green-700">
              Üzenet Küldése
            </button>
          </form>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  data() {
    return {
      team: [
        { name: 'Kovács János', role: 'Vezérigazgató', image: 'https://profile-images.xing.com/images/4f6d0b25c3f51a5a9005a77046e27041-1/rebecca-levesque.256x256.jpg' },
        { name: 'Nagy Éva', role: 'Műszaki Igazgató', image: 'https://media.licdn.com/dms/image/v2/D5603AQH7VGj19tP_Cg/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1703192775109?e=2147483647&v=beta&t=ZeBpghlABGflHA5etDZ_-Hh3tlQZZYIhOofsQBV9DDo' },
        { name: 'Szabó Péter', role: 'Vezető Mérnök', image: 'https://profile-images.xing.com/images/8591fd5286ad9bf3a63328bb0d477277-4/rick-rainer-ludwig.256x256.jpg' },
      ],
      features: [
        { icon: '🌱', title: 'Fenntartható', description: 'Környezetbarát megoldások egy jobb jövőért' },
        { icon: '💡', title: 'Innovatív', description: 'Élvonalbeli technológia és megközelítés' },
        { icon: '📊', title: 'Adatvezérelt', description: 'Analitikán alapuló döntéshozatal' },
      ],
      testimonials: [
        { quote: 'Kiváló szolgáltatás és eredmények!', name: 'Kis Andrea', company: 'Tech Kft.' },
        { quote: 'Teljesen átalakította az energiafelhasználásunkat.', name: 'Tóth Gábor', company: 'Zöld Ipar Zrt.' },
      ],
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      console.log('Űrlap elküldve:', this.form)
    }
  }
}
</script>