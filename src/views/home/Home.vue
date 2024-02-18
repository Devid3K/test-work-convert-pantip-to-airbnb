<template>
  <div class="">
    <header class="fixed top-0 left-0 w-full lg:px-8  bg-white z-20">
      <div
        class="component-sm-hidden  flex px-8 gap-8 mt-4 z-10"
      >
        <div
          class="search-bar w-full p-2 pl-5 rounded-full hover:scale-110 flex gap-4 justify-left items-center shadow-lg"
        >
          <img class="h-6 w-6" src="../../assets/icons8-search-50.png" alt="" />
          <div class="">
            <h3 class="promt text-[16px]">ต้องการไปที่กระทู้ไหน</h3>
            <p class="promt font-normal text-gray-400 text-[12px]">
              สีลม บางรัก
            </p>
          </div>
        </div>
        <div
          class="h-[50px] w-[60px] rounded-full hover:scale-110 fliter-box flex m-auto justify-center items-center"
        >
          <img class="h-6 w-6" src="../../assets/icons8-filter-48.png" alt="" />
        </div>
      </div>

      <div class="component-md-hidden flex justify-between px-4 gap-4 py-4">
        <div class="left-navbar flex">
          <img class="h-14 w-14 mr-16 cursor-pointer" src="../../assets/download.png" alt="" />
        </div>
        <!-- mid-navbar -->
        <Transition name="popup">
          <div
            v-show="showComponent"
            class="flex w-full lg:w-[400px] py-2 px-2 rounded-full text-center border-[1px] shadow-md justify-center items-center whitespace-nowrap gap-4 truncate"
          >
            <div
              class="promt w-full hover:text-[#8e05d2] cursor-pointer font-medium truncate"
            >
              หมวดหมู่
            </div>
            <hr class="my-line" />
            <div
              class="promt w-32 hover:text-[#8e05d2] cursor-pointer font-medium truncate"
            >
              วันที่
            </div>
            <hr class="my-line" />
            <div
              class="flex w-full promt font-light whitespace-nowrap text-center justify-between items-center truncate"
            >
              <div>
                <p class="truncate whitespace-nowrap w-20 promt outline-none border-0 text-slate-400">ผู้เขียน</p>
              </div>
              <div>
                <img
                  class="h-10"
                  src="../../assets/icons8-search-65.png"
                  alt=""
                />
              </div>
            </div>
          </div>
        </Transition>
        <!-- mid-navbar -->
        <div
          class="flex text-center items-center justify-center whitespace-nowrap promt lg:ml-12"
        >
          <a class="hover:text-[#8e05d2] cursor-pointer">เข้าสู่ระบบ /</a>
          <a class="ml-1 hover:text-[#8e05d2] cursor-pointer">สมัครสมาชิก</a>
          <div
            class="h-12 px-6 w-24 border-2 ml-4 rounded-full flex items-center justify-center gap-4"
          >
            <img class="h-6 cursor-pointer hover:bg-slate-200 rounded-full" src="../../assets/icons8-filter-30.png" alt="" />
            <img class="h-8 cursor-pointer hover:bg-slate-200 rounded-full" src="../../assets/user-1.png" alt="" />
          </div>
        </div>
      </div>
      <Transition name="slide" v-show="!showComponent">
        <Searchbar class="component-md-hidden lg:mt-[-65px]" />
      </Transition>
      <Category 
      :categorys="categorys"
      />
    </header>
    <Contents 
    :highlights="highlights"
    class="pt-[250px] md:pt-[370px] md:p-2 lg:px-8 lg:pt-[280px] z-0" />
    <SmFooter class="component-sm-hidden" />
  </div>
</template>

<script>
import axios from "axios";
import Category from "./category.vue";
import Contents from "./contents.vue";
import SmFooter from "./smfooter.vue";
import Searchbar from "./searchbar.vue";
export default {
  components: {
    Category,
    Contents,
    SmFooter,
    Searchbar,
  },
  data() {
    return {
      lastScrollPosition: 0,
      showComponent: false,
      highlights: null,
      categorys: null,
    };
  },
  created() {
    this.fetchData();
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
      this.showComponent = scrollTop > this.lastScrollPosition;
      this.lastScrollPosition = scrollTop;
    },
    fetchData() {
      axios
        .get("https://pantip.com/api/forum-service/home/get_highlight", {
          headers: {
            Ptauthorize: 'Basic dGVzdGVyOnRlc3Rlcg==', 
          },
        })
        .then((res) => {
          if (res) {
            console.log(res.data.data);
            this.highlights = res.data.data;
          } else {
            console.log('eror');
          }
        });
    },
  },
};
</script>

<style scoped>
.my-line {
  margin-top: 4px;
  align-items: center;
  text-align: center;
  border: 10px;
  height: 30px;
  width: 1px;
  background-color: rgb(184, 180, 180);
}
.fliter-box {
  border-width: 1px;
}
.search-bar {
  border-width: 1px;
}
.promt {
  font-family: Prompt;
}
@media screen and (min-width: 768px) {
  .component-sm-hidden {
    display: none;
  }
}
@media screen and (max-width: 767px) {
  .component-md-hidden {
    display: none;
  }
}
.slide-enter-active {
  animation: bounce-in 0.1s;
}
.slide-leave-active {
  animation: bounce-in 0.1s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(0.5);
  }
  100% {
    transform: scale(1);
  }
}
.popup-enter-active {
  animation: pop-out 0.09s;
}
.popup-leave-active {
  animation: pop-out 0.09s reverse;
}
@keyframes pop-out {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(0.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
