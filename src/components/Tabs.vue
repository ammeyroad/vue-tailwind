<template>
  <div>
    <h2 class="font-bold text-blue-900 text-1xl">Vue Js Simple Tabs</h2>
    <div class="container mx-auto">
<ul class="flex justify-center space-x-2 text-white">
  <li>
    <button @click="activeTabOne" :class="tab1Class">
      Tab 1
    </button>
  </li>
  <li>
    <button @click="activeTabTwo" :class="tab2Class">
      Tab 2
    </button>
  </li>
  <li>
    <button @click="activeTabThree" :class="tab3Class">
      Tab 3
    </button>
  </li>
</ul>
      <div class="p-3 mt-6 bg-white border">
        <div v-show="tab === 1">
          Tab 1 Content show Lorem ipsum dolor sit amet consectetur adipisicing
          elit.
        </div>
        <div v-show="tab === 2">
          Tab 2 Content show Lorem ipsum dolor sit amet consectetur, adipisicing
          elit.
        </div>
        <div v-show="tab === 3">
          Tab 3 Content show Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Amet,
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tab: 1,
    };
  },
  methods: {
    activeTabOne() {
      this.tab = 1;
    },
    activeTabTwo() {
      this.tab = 2;
    },
    activeTabThree() {
      this.tab = 3;
    },
  },
  computed: {
    tab1Class() {
      return {
        'bg-red-500': this.tab === 1,
        'bg-purple-500': this.tab !== 1,
        'text-white': true,
        'px-4 py-2': true,
        'inline-block': true,
      };
    },
    tab2Class() {
      return {
        'bg-red-500': this.tab === 2,
        'bg-purple-500': this.tab !== 2,
        'text-white': true,
        'px-4 py-2': true,
        'inline-block': true,
      };
    },
    tab3Class() {
      return {
        'bg-red-500': this.tab === 3,
        'bg-purple-500': this.tab !== 3,
        'text-white': true,
        'px-4 py-2': true,
        'inline-block': true,
      };
    },
  },
};
</script>
