<template>
    <div class="d-flex justify-content-center">
      <div class="card" style="width: 16rem;">
        <div class="image-container">
          <img class="card-img-top" :src="img" alt="img">
          <img class="hover-img" :src="hoverImg" alt="hover-img">
        </div>
        <div class="card-body">
          <h5 class="card-title">Name: {{ name }}</h5>
          <p class="card-text type-info">Type: {{ type }}</p>
          <p class="card-text frame-type-info">Frame Type: {{ frameType }}</p>
          <p class="card-text overflow-scroll description-info" style="height: 90px;">Description: {{ desc }}</p>
        </div>
      </div>
    </div>
  </template>
<script>
export default {
    data(){
        return{
            isHovered: false,
            hoverImg: '/yu-gi-oh-back.png',
        }
    },
    name: 'CardComponent',
    props: {
        img: String,
        name: String,
        type: String,
        frameType: String,
        desc: String,
    },
};
</script>


<style lang="scss" scoped>

 .card {
  position: relative;
}

.image-container {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 100%;
}

.hover-img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.card:hover .hover-img {
  opacity: 1;
}

.card-img-top {
  width: 100%;
  height: auto;
  transition: transform 0.3s ease;
}

.card:hover .card-img-top {
  transform: scale(1.1);
}

.card-body {
  opacity: 1;
  transition: opacity 0.3s ease;
  background-color: #FFD700;
}

.card:hover .card-body {
  opacity: 0;
}
.card .hidden {
  opacity: 0;
  pointer-events: none;
}

.type-info,
.frame-type-info {
  opacity: 1;
  transition: opacity 0.3s ease;
}

.description-info {
  opacity: 0;
  width: 100%;
  transition: opacity 0.3s ease;
}
</style>