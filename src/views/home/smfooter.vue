<template>
  <div>
    <footer>
      <Transition
        v-show="showComponent"
        class="fixed bottom-0  w-full h-[70px] border-t-2 "
      >
        <div class="flex justify-center items-center text-center gap-10 bg-white">
          <div >
            <img class="h-8 " src="../../assets/icons8-search-32.png" alt="" />
            <p class="prompt text-[12px] font-medium text-[rgb(106,90,205)]">ค้นหา</p>
          </div>
          <div >
            <img class="h-8 m-auto" src="../../assets/icons8-compass-50.png" alt="" />
            <p class="prompt text-[12px] font-medium">Explore</p>
          </div>
          <div >
            <img class="h-8 " src="../../assets/user-1.png" alt="" />
            <p class="prompt text-[12px] font-medium">ค้นหา</p>
          </div>
        </div>
      </Transition>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lastScrollPosition: 0,
      showComponent: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    this.handleScroll();
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollTop =
        window.pageYOffset || document.documentElement.scrollTop;
      this.showComponent = scrollTop < this.lastScrollPosition;
      this.lastScrollPosition = scrollTop;
    },
  },
};
</script>

<style scoped>
.prompt {
  font-family: Prompt;
}
.v-enter-active,
.v-leave-active {
  height: -200px;
  transition-duration: 300ms;
}

.v-enter-from,
.v-leave-to {
  height: 0px;
  transition-duration: 100ms;
}
</style>
