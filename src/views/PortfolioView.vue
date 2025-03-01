<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: "PKK",
          imageUrl: "Learn4Ward.png",
          status:
            "Learn4ward ini dibuat pada Januari 2025 sebagai bagian dari upaya modernisasi pendidikan dan peningkatan kualitas pembelajaran berbasis teknologi.",
          category: "UI/UX Design",
          github: "null",
          demo: "https://www.figma.com/design/76tcYYu1fTexpA4PB1cNtY/Tugas-PKK?node-id=0-1",
        },
        {
          id: 2,
          name: "PKL",
          imageUrl: "PTSAI.png",
          status:
            "Pengembangan Sistem Informasi Warga Berbasis Website Dalam Lingkup Rukun Tetangga dan Rukun Warga.",
          category: "UI/UX Design",
          github: "null",
          demo: "https://www.figma.com/design/JJRihr2G11BrAmicbdL078/PROJECT-SAI?node-id=0-1&p=f&t=US38Car7ku6uTzjc-0",
        },
        {
          id: 3,
          name: "TOIEC",
          imageUrl: "TOEIC.jpg",
          status: "Test of English for International Communication (920)",
          category: "Sertifikat",
          github: "null",
          demo: "null",
        },
        {
          id: 4,
          name: "Generative AI Microsoft",
          imageUrl: "GenerativeAI.png",
          status: "Pemahaman dan keterampilan dalam teknologi Artificial Intelligence (AI) dalam bidang Generative AI, serta cara menggunakannya dalam pengembangan aplikasi dan bisnis.",
          category: "Sertifikat",
          github: "null",
          demo: "null",
        },
        {
          id: 5,
          name: "PKL",
          imageUrl: "GitSAI.png",
          status:"Pengembangan Sistem Informasi Warga Berbasis Website Dalam Lingkup Rukun Tetangga dan Rukun Warga.",
          category: "Front-End / Web Development",
          github: "https://github.com/irfannurfirmansyah/informasi_warga",
          demo: "null",
        },
      ],
    };
  },
  computed: {
    groupedItems() {
      return this.items.reduce((acc, item) => {
        if (!acc[item.category]) {
          acc[item.category] = [];
        }
        acc[item.category].push(item);
        return acc;
      }, {});
    },
  },
};
</script>

<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-white mx-3">
    <article data-page="about">
      <header>
        <div
          class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col"
        >
          <h4>Portofolio</h4>
          <h4
            class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-teal-300 to-blue-300"
          >Proyek Terbaik yang Mewakili Kemampuan Saya
          </h4>
        </div>
      </header>

      <section>
        <div v-for="(projects, category) in groupedItems" :key="category">
          <!-- Kategori -->
          <h3 class="text-xl font-semibold text-white mb-3">{{ category }}</h3>

          <div  
            class="grid grid-cols-1 gap-4 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in"
          >
            <div v-for="item in projects" :key="item.id">
              <div
                class="item-card flex flex-col items-center gap-2 bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-white md:gap-3 px-5 py-5 lg:px-5"
              >
                <div
                  class="flex items-center justify-center p-0 h-full w-full lg:p-0 zoom-in"
                >
                  <img
                    :src="'/img/' + item.imageUrl"
                    alt="Project Image"
                    class="drop-shadow-xl rounded-xl"
                  />
                </div>
                <div
                  class="w-full flex flex-col gap-2 items-center text-sm md:text-base lg:text-lg"
                >
                  <div class="title-text font-medium text-secondary">
                    {{ item.name }}
                  </div>
                  <div
                    class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm"
                  >
                    {{ item.status }}
                  </div>
                  <div class="w-full flex justify-end">
                    <div
                      class="flex cursor-pointer items-end gap-2 text-primary"
                    >
                      <a
                        v-if="item.github !== 'null'"
                        :href="item.github"
                        target="_blank"
                        rel="noreferrer"
                        title="View GitHub repository"
                        class="transition-all hover:text-accent"
                      >
                        <svg
                          stroke="currentColor"
                          fill="none"
                          stroke-width="2"
                          viewBox="0 0 24 24"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          height="16"
                          width="16"
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
                          ></path>
                        </svg>
                      </a>
                      <a
                        v-if="item.demo !== 'null'"
                        :href="item.demo"
                        target="_blank"
                        rel="noreferrer"
                        title="View finished project"
                        class="transition-all hover:text-accent"
                      >
                        <svg
                          stroke="currentColor"
                          fill="none"
                          stroke-width="2"
                          viewBox="0 0 24 24"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          height="18"
                          width="18"
                          xmlns="http://www.w3.org/2000/svg"
                        >
                          <path
                            d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                          ></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                          <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Divider -->
          <div class="border-b border-teal-400 my-6"></div>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}
svg:hover {
  stroke: #ffdb70;
}
.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>
