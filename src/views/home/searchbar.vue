<template>
  <div>
    <div class="px-14 lg:px-[250px] ">
      <div
        class="flex gap-8 justify-center items-center mb-4 whitespace-nowrap truncate "
      >
        <button
          class="prompt w-max px-8 rounded-full h-12 cursor-pointer  hover:bg-slate-100 font-semibold"
          type=""
        >
          My Feed
        </button>
        <button
          class="prompt w-max px-8 rounded-full h-12  cursor-pointer hover:bg-slate-100"
          type=""
        >
          แลกพอยต์
        </button>
        <button
          class="prompt w-max px-8 rounded-full h-12 cursor-pointer hover:bg-slate-100"
          type=""
        >
          กิจกรรมพันทิป
        </button>
      </div>

      <div>
        <div
          class="flex whitespace-nowrap cursor-pointer justify-between bg-white border-[1px] shadow-md rounded-full truncate"
        >
          <div
            class="prompt w-full pl-6 lg:pl-10 rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
          >
            <h5 class="prompt ">หมวดหมู่</h5>
            <p class="prompt font-light">แนวของกระทู้</p>
          </div>

          <div class="flex w-full cursor-pointer">
            <div
              class="prompt w-full rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
              type=""
            >
              <h5 class="prompt cursor-pointer">วันที่</h5>
              <p class="prompt font-light">เลือกวันที่</p>
            </div>

            <div
              class="prompt cursor-pointer w-full rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
              type=""
            >
              <h5 class="prompt ">กระทู้แนะนำ</h5>
              <p class="prompt font-light">เลือกกระทู้</p>
            </div>
          </div>

          <div
            class="prompt flex cursor-pointer justify-between w-full rounded-full h-16 py-2 pr-4 hover:bg-slate-100 font-semibold"
            type=""
          >
            <div class="flex ">
              <div>
                <h5 class="prompt ">ผู้เขียน</h5>
                <p class="prompt font-light">ค้นหาผู้เขียน</p>
              </div>
            </div>
            <button class="flex justify-end items-end">
                <img
                  class="h-12"
                  src="../../assets/icons8-search-65.png"
                  alt=""
                />
              </button>
          </div>
        </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.prompt {
  font-family: Prompt;
}
.my-line {
  margin-top: 16px;
  align-items: center;
  text-align: center;
  border: 10px; /* ไม่ใช้เส้นขอบ */
  height: 30px; /* ความสูงของเส้น */
  width: 1px;
  background-color: rgb(184, 180, 180); /* สีของเส้น */
}
@media screen and (max-width: 767px) {
  .component-md-hidden {
    display: none;
  }
}
</style>
