<template>
  <transition enter-active-class="animated fadeInDown" leave-active-class="animated fadeOutRight">
    <div v-show="show" class="bubble">
      <div class="message">{{text}}</div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Notification",
  props: { text: { type: String, defaul: "" } },
  data() {
    return {
      show: false
    };
  },
  mounted() {
    this.show = true;
    setTimeout(() => {
      this.show = false;
    }, 3000);
  }
};
</script>

<style lang="scss" scoped>
.bubble {
  border-radius: 6px;
  position: absolute;
  top: 10%;
  padding: 5px 10px 5px 10px;
  background-color: $blue;
}

.message {
  @include medium-text;
  color: $white;

  display: flex;
  justify-content: center;
  align-items: center;
}
</style>