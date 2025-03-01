<script>
export default {
  data() {
    return {
      activeTab: 1,
      figma: require('@/assets/figma.png'),
      tech: [
        {
          id: 1,
          name: 'HTML',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png',
          status: 'Novis'
        },
        {
          id: 2,
          name: 'CSS',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png',
          status: 'Novis'
        },
        {
          id: 3,
          name: 'VueJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp',
          status: 'Pemula'
        },
        {
          id: 4,
          name: 'Tailwind',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg',
          status: 'Pemula'
        },
      ],
      tools: [
        {
          id: 1,
          name: 'Git',
          imageUrl: 'https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png',
          status: 'Professional Git Puller'
        },
        {
          id: 2,
          name: 'GitHub',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/25/25231.png',
          status: 'Professional Copy Url'
        },
        {
          id: 3,
          name: 'Figma',
          imageUrl: require('@/assets/figma.png'),
          status: 'Berpengalaman'
        },
      ]
    };
  }
}
</script>

<template>
  <div class="bg-[#1e1e1f] px-5 py-5 md:px-12 md:py-10 text-left border border-teal-500 rounded-3xl text-white mx-3 mb-5">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          About Me &nbsp;
          <div class="h-[1px] w-32 bg-teal-300 md:w-96 aos-init aos-animate" data-aos="zoom-in-left" data-aos-duration="600"></div>
        </div>
      </header>

      <section class="text-sm md:text-lg text-justify flex flex-col gap-4 md:flex-row md:gap-8 md:justify-center md:items-center">
       <!-- Foto -->
<div class="flex justify-center">
  <img class="w-40 h-40 md:w-60 md:h-60 rounded-lg object-cover fadein-up"
       :src="require('@/assets/FAST2.jpeg')" alt="Foto">
</div>

        <!-- Video -->
        <div class="flex justify-center">
          <video autoplay loop muted playsinline class="w-full max-w-md md:max-w-lg h-auto rounded-xl shadow-lg fadein-up">
            <source :src="require('@/assets/MAX2.mp4')" type="video/mp4">
            Browser tidak mendukung video.
          </video>
        </div>

        <!-- Deskripsi -->
        <div class="md:w-7/12">
          <p class="mb-3 md:mb-7 fadein-left fadeins-1">
            &nbsp; &nbsp; &nbsp; Seorang UI/UX Designer yang berkomitmen untuk menciptakan pengalaman digital yang relevan, intuitif, dan engaging. Bagi saya, desain bukan hanya soal estetika, tetapi bagaimana suatu produk bisa benar-benar relate dengan kebutuhan dan perilaku pengguna.
          </p>
          <p class="mb-3 fadein-left fadeins-2">
            &nbsp; &nbsp; &nbsp; Dengan pendekatan berbasis riset, saya selalu memastikan bahwa setiap desain yang saya buat tidak hanya terlihat menarik, tetapi juga mudah digunakan, fungsional, dan memberikan solusi nyata.
          </p>
        </div>
      </section>
    </article>
  </div>

  <!-- SKILLS SECTION -->
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-white mx-3">
    <article data-page="skills">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-teal-300 md:w-20 aos-init aos-animate" data-aos="zoom-in-left" data-aos-duration="600"></div>
          &nbsp; Skills
        </div>
      </header>
      
      <section>
        <div>
          <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400 mb-5">
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-white bg-teal-500 bg-opacity-85': activeTab === 1 }" @click="activeTab = 1">Bahasa Pemrograman</button>
            </li>
            <li class="mr-2">
              <button class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{ 'text-white bg-teal-500 bg-opacity-85': activeTab === 2 }" @click="activeTab = 2">Alat</button>
            </li>
          </ul>
        </div>

        <div v-show="activeTab === 1">
          <div class="grid grid-cols-2 gap-4 md:grid-cols-3 xl:grid-cols-4">
            <div v-for="item in tech" :key="item.id" class="group item-tech flex items-center gap-2 rounded border border-teal-500 px-2 py-2 hover:bg-white hover:bg-opacity-10">
              <img class="h-12 w-12 transition-transform duration-300 group-hover:scale-110" :src="item.imageUrl" alt="icon">
              <div class="text-sm md:text-base lg:text-lg">
                <div class="font-medium">{{ item.name }}</div>
                <div class="status-tech opacity-0 transition-opacity duration-300 group-hover:opacity-100 text-xs text-gray-300">
                  {{ item.status }}
                </div>
              </div>
            </div>
          </div>
        </div>

        <div v-show="activeTab === 2">
          <div class="grid grid-cols-2 gap-4 md:grid-cols-3 xl:grid-cols-4">
            <div v-for="item in tools" :key="item.id" class="group item-tech flex items-center gap-2 rounded border border-teal-500 px-2 py-2 hover:bg-white hover:bg-opacity-10">
              <img class="h-12 w-12 transition-transform duration-300 group-hover:scale-110" :src="item.imageUrl" alt="icon">
              <div class="text-sm md:text-base lg:text-lg">
                <div class="font-medium">{{ item.name }}</div>
                <div class="status-tech opacity-0 transition-opacity duration-300 group-hover:opacity-100 text-xs text-gray-300">
                  {{ item.status }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>
