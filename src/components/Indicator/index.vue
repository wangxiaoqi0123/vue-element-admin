<template>
  <div class="indicator-container middle">
    <transition name="fade">
      <div
        v-show="visible"
        class="indicator"
      >
        <div id="preloader_1">
          <span />
          <span />
          <span />
          <span />
          <span />
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'Toast',
  data () {
    return {
      visible: false,
      message: '',
      position: ''
    }
  }
}
</script>

<style scoped>
.indicator-container {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
}
.indicator {
  word-wrap: break-word;
  z-index: 9999;
  font-size: 14px;
  line-height: 15px;
  color: #fff;
  pointer-events: none;
  text-align: center;
  opacity: 1;
  min-width: 80px;
  min-height: 80px;
  max-width: 60%;
  text-align: center;
}

.middle {
  align-items: center;
}
i {
  font-style: normal;
  display: block;
  margin: 8px;
  max-height: 100px;
  box-sizing: border-box;
}
.fade-enter-active,
.fade-leave-active {
  transition: margin-top 0.2s, opacity 0.2s;
}

.fade-enter,
.fade-leave-active {
  margin-top: 40px;
  opacity: 0;
}

#preloader_1 {
  position: relative;
}

#preloader_1 span {
  display: block;
  bottom: 0px;
  width: 10px;
  height: 5px;
  background: #9b59b6;
  position: absolute;
  animation: preloader_1 1.5s infinite ease-in-out;
}

#preloader_1 span:nth-child(2) {
  left: 11px;
  animation-delay: 0.2s;
}

#preloader_1 span:nth-child(3) {
  left: 22px;
  animation-delay: 0.4s;
}

#preloader_1 span:nth-child(4) {
  left: 33px;
  animation-delay: 0.6s;
}

#preloader_1 span:nth-child(5) {
  left: 44px;
  animation-delay: 0.8s;
}

@keyframes preloader_1 {
  0% {
    height: 5px;
    transform: translateY(0px);
    background: #9b59b6;
  }
  25% {
    height: 30px;
    transform: translateY(15px);
    background: #3498db;
  }
  50% {
    height: 5px;
    transform: translateY(0px);
    background: #9b59b6;
  }
  100% {
    height: 5px;
    transform: translateY(0px);
    background: #9b59b6;
  }
}
</style>
