<template>
  <main>
    <section class="section">
      <strong class="text-3xl inline-block mb-8">
        <button
          class="inline-block cursor-pointer rounded-md bg-gray-800 px-4 py-3 text-center text-sm font-semibold uppercase text-white transition duration-200 ease-in-out hover:bg-gray-900"
        >
          Buttonsa
        </button>
        <div class="tooltip" data-tip="hello">
          <button class="btn">Hover me</button>
        </div>

        Wellcome to<span class="text-green-500"> Vue </span
        ><span class="text-pink-500">Tailwind</span> 👏🏻
      </strong>
	  <tabs />
      <div class="tabs tabs-boxed">
        <a class="tab">Tab 1</a>
        <a class="tab tab-active">Tab 2</a>
        <a class="tab">Tab 3</a>
      </div>
      <!-- Open the modal using ID.showModal() method -->
      <button class="btn" onclick="my_modal_2.showModal()">open modal</button>
      <dialog id="my_modal_2" class="modal">
        <div class="modal-box">
          <h3 class="font-bold text-lg">Hello!</h3>
          <p class="py-4">Press ESC key or click outside to close</p>
        </div>
        <form method="dialog" class="modal-backdrop">
          <button>close</button>
        </form>
      </dialog>
      <p class="mb-5">
        A simple starter template for Vue JS 3 + TailwindCSS and any other tools
      </p>
      <a
        href="https://github.com/or-abdillh/vue-tailwind.git"
        target="_blank"
        class="bg-gray-600 hover:bg-opacity-75 focus:ring-2 text-gray-50 px-5 py-2 rounded-lg inline-block"
      >
        <i class="fab fa-github"></i>
        <span class="mx-2">Github</span>
      </a>
    </section>

    <section class="section flex flex-col items-center gap-3">
      <small>Current click</small>
      <h1 class="text-5xl font-medium">{{ count.count }}</h1>
      <div class="flex gap-4 mt-3">
        <button @click="count.click()" class="btn-count">Click++</button>
        <button @click="count.doubleClick()" class="btn-count">
          Click * 2
        </button>
      </div>
    </section>

    <section class="mb-6">
      <h1 class="text-xl mb-3">
        <i class="fa fa-chevron-right"></i>
        Routes
      </h1>
      <div class="flex gap-4">
        <template v-for="(route, i) in routes" :key="i">
          <a
            @click="movePage(route.to)"
            class="text-green-500 text-lg hover:text-green-200 duration-300"
            >{{ route.name }}</a
          >
        </template>
      </div>
    </section>

    <section>
      <h1 class="text-xl">
        <i class="fa fa-chevron-right"></i>
        All dependencies
      </h1>
      <div class="flex flex-wrap gap-2 mt-3">
        <template v-for="(item, x) in dependencies" :key="x">
          <Pill :label="item" />
        </template>
      </div>
    </section>
    <Footer />
  </main>
</template>

<script setup>
import { useCount } from "@/stores/counter";
import { useRouter } from "vue-router";
import Pill from "@/components/Pill.vue";
import Footer from "@/components/Footer.vue";
import Tabs from "@/components/Tabs.vue";


const count = useCount();
const router = useRouter();

const movePage = (to) => router.push({ name: to });

const dependencies = [
  "Vue v.3.2.25",
  "Tailwindcss v.3.0.18",
  "Vue router v.4.0.12",
  "Pinia v.2.0.10",
  "Vite v.2.7.2",
  "Postcss v.8.4.5",
  "Autoprefixer v.10.4.2",
];

const routes = [
  {
    name: "About",
    to: "About",
  },
  {
    name: "Blank screen",
    to: "Blank",
  },
];
</script>

<style scoped>
.section {
  @apply w-full bg-gray-50 py-8 px-5 rounded mb-8;
}

.btn-count {
  @apply px-3 py-1 bg-indigo-400 text-gray-50 rounded;
}
</style>
