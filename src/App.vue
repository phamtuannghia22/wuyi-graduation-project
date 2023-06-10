<template>
  <div id="home" class="max-with-1125 container-fluid">
    <h1 class="my-2">
      Tứ phủ
    </h1>
    <div class="row">
      <div class="col-8 pe-0 h-80vh">
        <video controls autoplay="autoplay" loop="loop" preload="preload" poster="../src/assets/logo.svg">
          <source src="../src/assets/my-treasure.mp4" type="video/mp4">
          <source src="../src/assets/my-treasure.mp4" type="video/ogg">
          Your browser does not support the video tag.
        </video>
      </div>
      <div class="col-4 bg-blue ps-0">
        <BookTickets></BookTickets>
      </div>
    </div>
  </div>
</template>
<script>
import BookTickets from "@/components/BookTickets.vue";

export default {
  name: "App",
  components: {BookTickets},

};
</script>

<style scoped>
#home {
  font-size: 15px;
}

video {
  width: 100%;
  height: 100%;
}
.h-80vh {
  height: 88vh;
}
</style>
