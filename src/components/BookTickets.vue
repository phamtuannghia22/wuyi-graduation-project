<template>
  <div class="d-flex justify-content-center align-items-center h-100 position-relative">
    <div class="m-auto w-75 d-grid pt-2">
      <div class="waviy d-flex justify-content-center mb-2">
        <span style="--i: 1;">Đ</span>
        <span style="--i: 2;">Ặ</span>
        <span class="mr-2" style="--i: 3;">T</span>
        <span style="--i: 4;">V</span>
        <span class="mr-2" style="--i: 5;">É</span>
        <span style="--i: 6;">N</span>
        <span style="--i: 7;">G</span>
        <span style="--i: 8;">A</span>
        <span style="--i: 9;">Y</span>
      </div>
      <div class="p-3 bg-white mb-3 border rounded">
        <b-form-input size="sm" class="mb-2" placeholder="Họ và tên" v-model="user.name"></b-form-input>
        <b-form-input size="sm" class="mb-2" placeholder="Số điện thoại" v-model="user.phone"></b-form-input>
        <b-form-input size="sm" class="mb-2" placeholder="Email" v-model="user.email"></b-form-input>
        <b-form-textarea class="max-height mb-2 p-2" placeholder="Tin nhắn của bạn" v-model="user.messsage"></b-form-textarea>
        <div class="d-flex justify-content-center">
          <b-button size="sm" class="mx-auto" @click="send()">Gửi <b-icon class="ml-1" icon="arrow-right" animation="cylon" font-scale="1"></b-icon> </b-button>
        </div>
      </div>
      <p class="text-center fw-bold text-pink text-uppercase mb-1">hoặc liên hệ</p>
      <a href="mailto:tuphucongdong@gmail.com" class="text-white text-decoration-none">
        <p class="text-center text-white mb-1 font-size-13">tuphucongdong@gmail.com</p>
      </a>
      <p class="text-center text-pink mb-0">Cảm ơn đã ghé thăm!</p>
    </div>
    <b-icon class="ml-1 text-white position-absolute close-icon" icon="dash-circle" font-scale="1" @click="$bvModal.hide('modal-book-tickets')"></b-icon>
  </div>
</template>
<script>
export default {
  name: "BookTickets",
  data() {
    return {
      user: {
        name: "",
        phone: "",
        email: "",
        messsage: "",
      },
    };
  },
  methods: {
    send() {
      if (this.user.name.length == 0) {
        return this.$bvToast.toast("Vui lòng nhập họ và tên của bạn !", {
          title: "Cảnh báo",
          autoHideDelay: 3000,
          variant: "warning",
          toaster: "b-toaster-top-right",
        });
      }
      if (this.user.phone.length == 0 && this.user.email.length == 0) {
        return this.$bvToast.toast("Vui lòng nhập thông tin liên lạc để chúng tôi có thể  gửi thông tin cho bạn !", {
          title: "Cảnh báo",
          autoHideDelay: 3000,
          variant: "warning",
          toaster: "b-toaster-top-right",
        });
      }
      this.$bvToast.toast("Đặt vé thành công ! Thông tin sự kiện sẽ được gửi đến bạn trong vài giờ tới. Chân thành cảm ơn", {
        title: "Thông báo",
        autoHideDelay: 5000,
        variant: "success",
        toaster: "b-toaster-top-right",
      });
    },
  },
};
</script>

<style scoped>
button {
  background: var(--wuyi-pink);
}

button:hover {
  background: #ad2e56ff;
}
.max-height {
  height: 68px;
  max-height: 68px !important;
}
.waviy {
  position: relative;
  font-size: 28px;
}
.waviy span {
  font-weight: bold;
  width: fit-content;
  position: relative;
  color: #fff;
  text-transform: uppercase;
  /*animation: waviy 1s infinite;*/
  /*animation-delay: calc(.1s * var(--i));*/
  animation: flip 2s infinite;
  animation-delay: calc(0.2s * var(--i));
  color: var(--wuyi-pink);
}
/*@keyframes waviy {*/
/*  0%,40%,100% {*/
/*    transform: translateY(0)*/
/*  }*/
/*  20% {*/
/*    transform: translateY(-20px)*/
/*  }*/
/*}*/

@keyframes flip {
  0%,
  80% {
    transform: rotateY(360deg);
  }
}

.close-icon {
  top: 0px;
  right: 0px;
  cursor: pointer;
}

</style>
