<template>
  <div>
    <div class="md:border-t-[1px] pl-5 pr-5 mt-6 pb-1 md:flex w-full  gap-8 justify-between overflow-x-scroll md:border-b-[1px] shadow-sm">
      <!-- sm-category -->
      <div
        class="w-full md:w-full component-sm-hidden border-b-[1px] shadow-sm overflow-x-scroll overflow-y-hidden flex gap-4 no-scrollbar  relative"
      >
        <div
          v-for="category in categorys"
          class="w-full p-2 cursor-pointer hover:scale-110 duration-200 hover:bg-slate-200 promt rounded-lg pt-1 text-center whitespace-nowrap"
        >
          <img class="m-auto h-8" :src="category.img_src" alt="" />

          <p class="font-bold">{{ category.name }}</p>
        </div>
      </div>
      <div
          class="btn border-[1px] component-sm-hidden w-full h-16 mt-4 mb-4 px-4 rounded-xl flex gap-2 promt transition ease-in-out delay-150 hover:bg-slate-200 duration-150 whitespace-nowrap justify-between items-center text-center "
        >
          <p class="cursor-default font-medium">แสดงกระทู้ที่ยังไม่ได้ปิดอ่าน</p>
          <label class="switch">
            <input type="checkbox" />
            <span class="slider round"></span>
          </label>
        </div>
      <!-- md-category -->
      
      <Carousel class=" component-md-hidden  no-scrollbar mt-4 "/>

      <!-- filter -->
      <div
        class="flex justify-between lg:justify-end w-full lg:w-auto mt-4 gap-4 h-14 component-md-hidden bg-transparent"
      >
        <div
          class="btn cursor-pointer transition ease-in-out delay-150 hover:bg-slate-200 duration-150 w-max px-4 border-[1px] rounded-3xl flex gap-2 promt whitespace-nowrap items-center text-center"
        >
          <img class="h-6" src="../../assets/icons8-filter-48.png" alt="" />
          <p>ตัวกรอง</p>
        </div>
        <div
          class="btn border-[1px] px-4 rounded-3xl flex gap-2 promt transition ease-in-out delay-150 hover:bg-slate-200 duration-150 whitespace-nowrap items-center text-center"
        >
          <p class="cursor-default">แสดงกระทู้ที่ยังไม่ได้ปิดอ่าน</p>
          <label class="switch">
            <input type="checkbox" />
            <span class="slider round"></span>
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import img1 from "../../assets/1.png";
import img2 from "../../assets/2.png";
import img3 from "../../assets/3.png";
import img4 from "../../assets/4.png";
import img5 from "../../assets/5.png";
import Carousel from './carousel.vue';
export default {
  components: {
    Carousel,

  },
  data() {
    return {
      categorys: [
        {
          id: 10,
          name: "ซิลิคอนวัลเลย์",
          name_en: "siliconvalley",
          slug: "siliconvalley",
          is_pinned: false,
          img_src: img1,
        },
        {
          id: 16,
          name: "มาบุญครอง",
          name_en: "mbk",
          slug: "mbk",
          img_src: img2,
          is_pinned: false,
        },
        {
          id: 25,
          name: "สีลม",
          name_en: "silom",
          slug: "silom",
          img_src: img3,
          is_pinned: false,
        },
        {
          id: 26,
          name: "หว้ากอ",
          name_en: "wahkor",
          slug: "wahkor",
          img_src: img4,
          is_pinned: false,
        },
        {
          id: 6,
          name: "เฉลิมกรุง",
          name_en: "chalermkrung",
          slug: "chalermkrung",
          img_src: img5,
          is_pinned: false,
        },
        {
          id: 9,
          name: "ชายคา",
          name_en: "home",
          slug: "home",
          img_src: img1,
          is_pinned: false,
        },
        {
          id: 2,
          name: "ก้นครัว",
          name_en: "food",
          slug: "food",
          img_src: img2,
          is_pinned: false,
        },
        {
          id: 100,
          name: "รวมมิตร",
          name_en: "all",
          slug: "",
          img_src: img3,
          is_pinned: false,
        },
        {
          id: 18,
          name: "ราชดำเนิน",
          name_en: "rajdumnern",
          slug: "rajdumnern",
          img_src: img4,
          is_pinned: false,
        },
        {
          id: 17,
          name: "รัชดา",
          name_en: "ratchada",
          slug: "ratchada",
          img_src: img5,
          is_pinned: false,
        },
        {
          id: 32,
          name: "บางรัก",
          name_en: "bangrak",
          slug: "bangrak",
          img_src: img1,
          is_pinned: false,
        },
        {
          id: 30,
          name: "การ์ตูน",
          name_en: "cartoon",
          slug: "cartoon",
          img_src: img2,
          is_pinned: false,
        },
      ],
      currentIndex: 0,
      slides: [1, 2, 3, 4],
      prevArrow: '<button class="slick-prev">Previous</button>',
      nextArrow: '<button class="slick-next">Next</button>',
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.slides.length;
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.slides.length) % this.slides.length;
    },
  },
};
</script>

<style scoped>
.promt {
  font-family: Prompt;
}
@layer utilities {
  @variants responsive {
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  }
}
@media screen and (max-width: 767px) {
  .component-md-hidden {
    display: none;
  }
}

@media screen and (min-width: 1079px) {
  .lg-hidden {
    display: none;
  }
}
@media screen and (min-width: 768px) {
  .component-sm-hidden {
    display: none;
  }
}
@media screen and (max-width: 1079px) {
  .component-lg-hidden {
    display: none;
  }
}
a {
  justify-content: center;
  justify-items: center;
  text-align: center;
  font-size: 25px;
  display: flex;
  width: 30px;
  height: auto;
}
a:hover {
  transform: scale(1.2);
  transition-duration: 300ms;
}
.bg-previous {
  background: linear-gradient(90deg, #ffffff, #ffffffca, #ffffff67, #ffffff00);
}
.bg-next {
  background: linear-gradient(90deg, #ffffff00, #ffffff67, #ffffffca, #ffffff);
}
.previous {
  background-color: transparent;
  color: black;
}
.next {
  background-color: #f1f1f1;
  color: black;
}
.round {
  border-radius: 100%;
}
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #2196f3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196f3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
.slide-item {
  transition: transform 1.5s ease-in-out;
}
.slide-item-enter-active {
  transition: transform 1.5s ease-in-out;
}
.slide-item-leave-active {
  transition: transform 1.5s ease-in-out;
}
.slide-item-enter {
  transform: translateX(-100%);
}
.slide-item-leave-to {
  transform: translateX(100%);
}
</style>
