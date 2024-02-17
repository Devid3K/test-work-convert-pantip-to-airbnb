<template>
  <div>
    <div class="md:grid grid-cols-2 lg:grid-cols-6">
        <div v-for="highlight in highlights" class="p-6">
          <div class="md:hover:scale-110 duration-200 cursor-pointer">
            <img class="rounded-xl m-auto md:hover:scale-110 duration-200 cursor-pointer" :src="highlight.image_url[2]" alt="" />
            <div class="mt-4 text-[18px]  h-14 line-clamp-2   promt font-medium">{{ highlight.name }}</div>
            <!-- <div class="flex gap-2 justify-center text-center items-center mt-2">
            <img class="h-8" src="../../assets/icons8-user-50.png" alt="" />
            <p class="promt font-light text-gray-500 truncate">
              ความคิดเห็นที่1:
              สำหรับสิ่งแรกที่หลายคนนั้นอาจไม่เคยรู้มาก่อนก็คือการปลูกต้นไม้จะทำให้คุณรู้สึกผ่อนคลายอย่างไม่น่าเชื่อ
              เนื่องจากว่าการปลูกทำให้คุณมีจิตใจสงบ
            </p>
          </div> -->
          </div>
        </div>
        <div v-for="highlight in highlights" class="p-6">
          <div class="md:hover:scale-110 duration-200 cursor-pointer">
            <img class="rounded-xl m-auto md:hover:scale-110 duration-200 cursor-pointer" :src="highlight.image_url[2]" alt="" />
            <div class="mt-4 text-[18px]  h-14 line-clamp-2   promt font-medium">{{ highlight.name }}</div>
          </div>
        </div>
        <div v-for="highlight in highlights" class="p-6">
          <div class="md:hover:scale-110 duration-200 cursor-pointer">
            <img class="rounded-xl m-auto md:hover:scale-110 duration-200 cursor-pointer" :src="highlight.image_url[2]" alt="" />
            <div class="mt-4 text-[18px]  h-14 line-clamp-2   promt font-medium">{{ highlight.name }}</div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    highlights: Array,
  },
  mounted() {
    console.log(this.highlights);
  },
};
</script>

<style scoped>
.line-clamp-2 {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
  -webkit-line-clamp: 2; 
}
.promt {
  font-family: Prompt;
}
</style>
