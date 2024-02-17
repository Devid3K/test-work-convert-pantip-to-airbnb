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
          class="flex whitespace-nowrap cursor-pointer text-center justify-between bg-white border-[1px] shadow-md rounded-full truncate"
        >
          <div
            class="prompt w-full  rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
          >
            <h5 class="prompt ">หมวดหมู่</h5>
            <p class="prompt font-light">แนวของกระทู้</p>
          </div>

          <div class="flex w-full cursor-pointer ">
            <div
              class="prompt w-full rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
              type=""
            >
              <h5 class="prompt cursor-pointer">วันที่</h5>
              <p class="prompt font-light">เลือกวันที่</p>
            </div>

            <div
              class="prompt cursor-pointer text-center w-full rounded-full h-16 py-2 hover:bg-slate-100 font-semibold"
              type=""
            >
              <h5 class="prompt ">กระทู้แนะนำ</h5>
              <p class="prompt font-light">เลือกกระทู้</p>
            </div>
          </div>

          <div
            class="prompt  flex cursor-pointer justify-center items-center w-full rounded-full h-16 py-2  hover:bg-slate-100 font-semibold"
          >
            <div class="flex  ">
              <div class="">
                <h5 class="prompt ">ผู้เขียน</h5>
                <p class="prompt font-light">ค้นหาผู้เขียน</p>
              </div>
            </div>
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
