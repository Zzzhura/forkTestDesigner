<script>
export default {
  methods: {
    zoomIn(event) {
      event.currentTarget.style.transform = 'scale(1.1)';
    },
    zoomOut(event) {
      event.currentTarget.style.transform = 'scale(1)';
    },

    SelectOption(option) {
      this.selected = option.name
      this.areaOpsionsVisible =!this.areaOpsionsVisible;
    },
  },
  modalImage: null,
  data() {
    return {
      images: [
        {url: "../src/images/project1/project1_1.png"},
        {url: "../src/images/project1/project1_2.png"},
        {url: "../src/images/project1/project1_3.png"},
        {url: "../src/images/project1/project1_4.png"},
        {url: "../src/images/project1/project1_5.png"},
        {url: "../src/images/project1/project1_6.png"},
        {url: "../src/images/project1/project1_7.png"},
        {url: "../src/images/project2/project2_1.png"},
        {url: "../src/images/project2/project2_2.png"},
        {url: "../src/images/project2/project2_3.png"},
        {url: "../src/images/project2/project2_4.png"},
        {url: "../src/images/project2/project2_5.png"},
        {url: "../src/images/project2/project2_6.png"},
        {url: "../src/images/project2/project2_7.png"},
        {url: "../src/images/project3/project3_1.png"},
        {url: "../src/images/project3/project3_2.png"},
        {url: "../src/images/project3/project3_3.png"},
        {url: "../src/images/project3/project3_4.png"},
        {url: "../src/images/project3/project3_5.png"},
        {url: "../src/images/project3/project3_6.png"},
        {url: "../src/images/project3/project3_7.png"},
        {url: "../src/images/project3/project3_8.png"},
        {url: "../src/images/project3/project3_9.png"},
        {url: "../src/images/project3/project3_10.png"}
      ],
      options: [
        {name: 'Консультация', value:1},
        {name: 'Полный дизайн-проект', value:2},
        {name: 'Планировочное решение', value:3},
        {name: 'Эскизный проект', value:4},
        {name: 'Авторский надзор', value:5},
      ],
      modalImage: null,
      modals: {
        consultation: false,
        designProject: false,
        planDecision: false,
        sketchyProject: false,
        authorsProject: false
      },
      pdfUrl: '../src/assets/our_docs/Мини_дизайн_проект_для_определения_стоимости.pdf',

      selected: 'Услуга',
      areaOpsionsVisible : false,

    };
  },
};
</script>

<template>
  <div class="portfolio">
    <nav>
      <p class="title">ПОРТФОЛИО</p>
      <div class="line_container">
        <img src="../src/images/line.png" class="line">
      </div>
      <div class="gallery">
        <div v-for="(image, index) in images" :key="index" @click="openModal(index)">
          <img :src="image.url" class="zoom-image" @mouseover="zoomIn" @mouseleave="zoomOut">
        </div>

        <!-- Модальное окно для отображения фото -->
        <div v-if='modalImage !== null' class="modal_window" @click="closeModal_img">
          <img :src="modalImage.url" class="modal-image">
        </div>
      </div>
    </nav>
  </div>
</template>

<style>

</style>