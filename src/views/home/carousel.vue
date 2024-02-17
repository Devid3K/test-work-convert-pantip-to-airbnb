<template>
  <carousel  class="overflow-x-scroll  ">
    <slide
      class="   overflow-y-hidden flex  no-scrollbar mt-4 "
    >
      <div
        v-for="category in categorys"
        class="w-full p-2 cursor-pointer hover:scale-110 duration-200 hover:bg-slate-200 promt rounded-lg pt-1 text-center whitespace-nowrap"
      >
        <img class="m-auto h-8" :src="category.img_src" alt="" />

        <p class="font-bold">{{ category.name }}</p>
      </div>
    </slide>
    <slide
      class="   overflow-y-hidden flex  no-scrollbar mt-4 "
    >
      <div
        v-for="category in categorys"
        class="w-full p-2 cursor-pointer hover:scale-110 duration-200 hover:bg-slate-200 promt rounded-lg pt-1 text-center whitespace-nowrap"
      >
        <img class="m-auto h-8" :src="category.img_src" alt="" />

        <p class="font-bold">{{ category.name }}</p>
      </div>
    </slide>
    <slide
      class="    overflow-y-hidden flex  no-scrollbar mt-4 "
    >
      <div
        v-for="category in categorys"
        class="w-full p-2 cursor-pointer hover:scale-110 duration-200 hover:bg-slate-200 promt rounded-lg pt-1 text-center whitespace-nowrap"
      >
        <img class="m-auto h-8" :src="category.img_src" alt="" />

        <p class="font-bold">{{ category.name }}</p>
      </div>
    </slide>
    <template #addons>
      <navigation class="rounded-full border-[1px]" />
    </template>
  </carousel>
</template>

<script>
import img1 from "../../assets/1.png";
import img2 from "../../assets/2.png";
import img3 from "../../assets/3.png";
import img4 from "../../assets/4.png";
import img5 from "../../assets/5.png";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

export default {
  name: "App",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
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
      ],
    };
  },
};
</script>
<style scoped>
.carousel__prev,
.carousel__next {
  background-color: red !important;
  border-radius: 100%;
  height: 100px !important;
  width: 80px !important;
  box-sizing: content-box;
  border: 50px solid white !important;
}
</style>
