<script>
// import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  data() {
    return {
      user : {
        name : '',
        phone : '',
        email : '',
        messsage : ''
      }
    }
  },
  methods : {
    send() {
      this.$bvToast.toast(`This is toast number`, {
        title: 'BootstrapVue Toast',
        autoHideDelay: 5000,
      })
    }
  }
}
</script>

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
        <div class="d-flex justify-content-center align-items-center h-100">
          <div class="m-auto w-75 d-grid">
            <h3 class="text-pink text-center mt-0 pt-0">ĐẶT VÉ NGAY</h3>
            <div class="p-3 bg-white mb-3 border rounded">
              <b-form-input size="sm" class="mb-2" placeholder="Họ và tên" v-model="user.name"></b-form-input>
              <b-form-input size="sm" class="mb-2" placeholder="Số điện thoại" v-model="user.phone"></b-form-input>
              <b-form-input size="sm" class="mb-2" placeholder="Email" v-model="user.email"></b-form-input>
              <b-form-textarea class="max-height mb-2 p-2" placeholder="Tin nhắn của bạn" v-model="user.messsage"></b-form-textarea>
              <div class="d-flex justify-content-center">
                <b-button size="sm" class="mx-auto" @click="send()">Gửi <i class="ms-1 bi bi-arrow-right"></i></b-button>
                
              </div>
            </div>
            <p class="text-center fw-bold text-pink text-uppercase mb-1">hoặc liên hệ</p>
            <p class="text-center text-white mb-1 font-size-13">tuphucongdong@gmail.com</p>
            <p class="text-center text-pink mb-0">Cảm ơn đã ghé thăm!</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
#home {
  font-size: 15px;
}
video {
  width: 100%;
  height: 100%;  
}
button {
  background: var(--wuyi-pink);
}
button:hover {
  background: #AD2E56FF;
}
.h-80vh {
  height: 88vh;
}
.max-height {
  height: 68px;
  max-height: 68px !important;
}
</style>
