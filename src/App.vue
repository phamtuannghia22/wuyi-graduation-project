<template>
  <div id="home">
    <header class="p-2 d-flex justify-content-between align-items-center">
      <img class="py-1 ml-2" src="../src/assets/logo-tuphu.svg" width="69">
      <b-button size="md" @click="$bvModal.show('modal-book-tickets')">Đặt vé <b-icon class="ml-1 my-auto" icon="person-plus" animation="throb" font-scale="1"></b-icon></b-button>
    </header>
    <div id="container-content" class="d-flex justify-content-center align-items-center">
      <div id="home" class="max-with-1125 container-fluid h-69vh">
        <video controls autoplay="autoplay" loop="loop" preload="preload" poster="../src/assets/poster.svg">
          <source src="../src/assets/my-treasure.mp4" type="video/mp4" />
          <source src="../src/assets/my-treasure.mp4" type="video/ogg" />
          Your browser does not support the video tag.
        </video>
      </div>
    </div>
    <footer class="py-3 d-flex justify-content-center align-items-center">
      <h4 class="text-center font-weight-bold text-pink"> Quỹ sẽ dành 30% nguồn lực cho các trại dành cho trẻ mồ côi</h4>
    </footer>
    <b-modal scrollable hide-footer id="modal-book-tickets" hide-header>
      <BookTickets></BookTickets>
    </b-modal>
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
header, footer {
  background: var(--wuyi-dark-blue);
}
#home {
  font-size: 15px;
}

button {
  background: var(--wuyi-pink);
  border: unset !important;
}
button:hover {
  background: #ad2e56ff;
}

button:focus {
  outline: none;
  box-shadow: none;
  background: var(--wuyi-pink);
}

video {
  width: 100%;
  height: 100%;
  background: black;
}

.h-69vh {
  height: 69vh;
}

#container-content {
  height: calc(100vh - 142px);
}

</style>
