<template>
  <header class="bg-orange-900 text-white shadow-md">
    <div class="max-w-7xl mx-auto px-4 py-4 flex items-center justify-between">
      <h1 class="text-3xl font-bold">Book Store</h1>
      <nav>
        <ul class="flex space-x-6 text-lg">
          <li><a href="#" class="hover:underline">Home</a></li>
          <li><a href="#" class="hover:underline">Bestsellers</a></li>
          <li><a href="#" class="hover:underline">Categories</a></li>
          <li><a href="#" class="hover:underline">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl px-4 py-16 sm:px-6 sm:py-24 lg:max-w-7xl lg:px-8">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">Bestsellers</h2>

      <div class="mt-6 grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">
        <div class="group p-2 shadow-lg border border-gray-300 rounded-lg" v-for="(item, index) in books">
          <div class="overflow-hidden">
            <img :src="item.image" alt="Front of men's Basic Tee in black."
              class="aspect-square w-full bg-gray-200 transition-transform duration-300 group-hover:scale-110" />
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-lg text-gray-700 font-bold">
                <a :href="item.url">
                  <span aria-hidden="true" class="absolute inset-0"></span>
                  {{ item.title }}
                </a>
              </h3>
            </div>
            <h3 class="text-red-900 font-bold">{{ item.price }}</h3>
          </div>
          <div class="mt-4 grid place-items-end">
            <a :href="item.url" class="bg-orange-900 p-1 rounded-md text-white place-items-end" target="_blank">Buy
              Now</a>
          </div>
        </div>
      </div>
      <!-- More products... -->
    </div>
  </div>
  <footer class="bg-gray-800 text-white py-6">
    <div class="max-w-7xl mx-auto px-4">
      <p class="text-center">© 2023 Book Store. All rights reserved.</p>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      books: [
        { title: 'Inside Deep Learning', image: new URL('@/assets/book1.png', import.meta.url).href, price: '20$', show: false, url: 'https://www.amazon.com/Wild-Dark-Shore-Charlotte-McConaghy-ebook/dp/B0D12WJTBY/ref=s9_acsd_al_ot_c2_x_0_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Inside Deep Learning Patterns and Practice', image: new URL('@/assets/book2.png', import.meta.url).href, price: '130$', show: false, url: 'https://www.amazon.com/Wild-Dark-Shore-Charlotte-McConaghy-ebook/dp/B0D12WJTBY/ref=s9_acsd_al_ot_c2_x_0_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Inside Deep Learning Patterns', image: new URL('@/assets/book3.png', import.meta.url).href, price: '40$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'The Hunger Game', image: new URL('@/assets/book4.jpg', import.meta.url).href, price: '50$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'SUZANNE COLLINS', image: new URL('@/assets/book5.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'THE HUNGER GAMES', image: new URL('@/assets/book6.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'DIVERGENTS SERIES', image: new URL('@/assets/book7.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Free Four Divergent', image: new URL('@/assets/book8.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Four The Inititate', image: new URL('@/assets/book9.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Allegiant Collector', image: new URL('@/assets/book10.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Four The Initiate', image: new URL('@/assets/book11.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },
        { title: 'Allegiant Collector', image: new URL('@/assets/book12.jpg', import.meta.url).href, price: '60$', show: false, url: 'https://www.amazon.com/Sunrise-Reaping-Hunger-Games-Novel-ebook/dp/B0D6BRYLL1/ref=s9_acsd_al_ot_c2_x_4_t?_encoding=UTF8&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=merchandised-search-4&pf_rd_r=EMPY8PQ7M6HZZSGKDF17&pf_rd_p=99a77863-1eba-4ff1-97ad-5ed960a83ac6&pf_rd_t=&pf_rd_i=283155' },

      ]
    }
  },
  methods: {
    toggleShow(book) {
      book.show = !book.show;
    },
    buyBook(url) {
      window.open(url, '_blank');
    }
  }
}
</script>