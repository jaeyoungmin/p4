<template>
  <v-row class="main d-flex justify-center align-center">
    <div class="main-item">
      M
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      I
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      N
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      J
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      A
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      E
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      Y
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      O
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      U
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      N
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="main-item">
      G
      <span></span>
      <span></span>
      <span></span>
      <span></span>
    </div>
  </v-row>
</template>

<script>
export default {
  name: 'Main',
};
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
h1 {
  font-size: 4rem;
  color: #fff;
  font-weight: normal;

  span.cursor.typing {
    animation: none;
  }
}
.main {
  height: 100vh;
  width: 100%;
}

.main-item {
  position: relative;

  display: flex;
  align-items: center;
  margin: 10px;
  justify-content: center;
  padding: 5px 10px;
  color: #03e9f4;
  font-size: 24px;
  text-decoration: none;
  text-transform: uppercase;
  transition: 0.5s;
  letter-spacing: 4px;
  overflow: hidden;
  -webkit-box-reflect: below 1px linear-gradient(transparent, #0005);
}

.main-item:hover {
  background: #03e9f4;
  color: #050801;
  box-shadow: 0 0 5px #03e9f4, 0 0 25px #03e9f4, 0 0 50px #03e9f4,
    0 0 100px #03e9f4;
}
.main-item:nth-child(1) {
  filter: hue-rotate(290deg);
}
.main-item:nth-child(3) {
  filter: hue-rotate(110deg);
}
.main-item:nth-child(4) {
  filter: hue-rotate(10deg);
}
.main-item:nth-child(5) {
  filter: hue-rotate(80deg);
}
.main-item:nth-child(6) {
  filter: hue-rotate(180deg);
}
.main-item:nth-child(7) {
  filter: hue-rotate(120deg);
}
.main-item:nth-child(8) {
  filter: hue-rotate(0deg);
}
.main-item:nth-child(9) {
  filter: hue-rotate(80deg);
}
.main-item:nth-child(10) {
  filter: hue-rotate(270deg);
}
.main-item:nth-child(11) {
  filter: hue-rotate(150deg);
}
.main-item span {
  position: absolute;
  display: block;
}
.main-item span:nth-child(1) {
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(90deg, transparent, #03e9f4);
  animation: animate1 1s linear infinite;
}
@keyframes animate1 {
  0% {
    left: -100%;
  }
  50%,
  100% {
    left: 100%;
  }
}
.main-item span:nth-child(2) {
  top: -100%;
  right: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(180deg, transparent, #03e9f4);
  animation: animate2 1s linear infinite;
  animation-delay: 0.25s;
}
@keyframes animate2 {
  0% {
    top: -100%;
  }
  50%,
  100% {
    top: 100%;
  }
}
.main-item span:nth-child(3) {
  bottom: 0;
  right: -100%;
  width: 100%;
  height: 2px;
  background: linear-gradient(270deg, transparent, #03e9f4);
  animation: animate3 1s linear infinite;
  animation-delay: 0.5s;
}
@keyframes animate3 {
  0% {
    right: -100%;
  }
  50%,
  100% {
    right: 100%;
  }
}
.main-item span:nth-child(4) {
  bottom: -100%;
  left: 0;
  width: 2px;
  height: 100%;
  background: linear-gradient(270deg, transparent, #03e9f4);
  animation: animate4 1s linear infinite;
  animation-delay: 0.75s;
}
@keyframes animate4 {
  0% {
    bottom: -100%;
  }
  50%,
  100% {
    bottom: 100%;
  }
}
</style>
