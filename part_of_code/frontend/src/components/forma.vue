<script>
import axios from "axios";
export default {
  name: "ModalButton",
  name_b: "V_celect",
  props: {
    selected: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      formData: {
        name: "",
        phone: "",
        service: "",
      },
      images: [
        { url: "../src/images/project1/project1_1.png" },
        { url: "../src/images/project1/project1_2.png" },
        { url: "../src/images/project1/project1_3.png" },
        { url: "../src/images/project1/project1_4.png" },
        { url: "../src/images/project1/project1_5.png" },
        { url: "../src/images/project1/project1_6.png" },
        { url: "../src/images/project1/project1_7.png" },
        { url: "../src/images/project2/project2_1.png" },
        { url: "../src/images/project2/project2_2.png" },
        { url: "../src/images/project2/project2_3.png" },
        { url: "../src/images/project2/project2_4.png" },
        { url: "../src/images/project2/project2_5.png" },
        { url: "../src/images/project2/project2_6.png" },
        { url: "../src/images/project2/project2_7.png" },
        { url: "../src/images/project3/project3_1.png" },
        { url: "../src/images/project3/project3_2.png" },
        { url: "../src/images/project3/project3_3.png" },
        { url: "../src/images/project3/project3_4.png" },
        { url: "../src/images/project3/project3_5.png" },
        { url: "../src/images/project3/project3_6.png" },
        { url: "../src/images/project3/project3_7.png" },
        { url: "../src/images/project3/project3_8.png" },
        { url: "../src/images/project3/project3_9.png" },
        { url: "../src/images/project3/project3_10.png" },
      ],
      options: [
        { name: "Консультация", name: "Консультация" },
        { name: "Полный дизайн-проект", name: "Полнный дизайн-проект" },
        { name: "Планировочное решение", name: "Планировочное решение" },
        { name: "Эскизный проект", name: "Эскизный проект" },
        { name: "Авторский надзор", name: "Авторский надзор" },
      ],
      selected: "Услуга",
      areaOpsionsVisible: false,

      modalImage: null,
      modals: {
        consultation: false,
        designProject: false,
        planDecision: false,
        sketchyProject: false,
        authorsProject: false,
      },
      pdfUrl:
        "../src/assets/our_docs/Мини_дизайн_проект_для_определения_стоимости.pdf",
    };
  },
  methods: {
    // Функция прокрутки веб-страницы до определенного класса (className) при нажатии на какую-либо кнопку в навигации

    forward(className, offset) {
      const element = document.querySelector(className);
      const topPos =
        element.getBoundingClientRect().top + window.pageYOffset - offset;
      window.scrollTo({ top: topPos, behavior: "smooth" });
    },
    //КОНЕЦ

    //Функции открытия и закрытия модального окна в услугах
    showModal(modal) {
      this.modals[modal] = true;
    },
    closeModal(modal) {
      this.modals[modal] = false;
    },

    // КОНЕЦ
    //Ф-ции открытия и закрытия окна с фоткой в портфолио
    openModal(index) {
      this.modalImage = this.images[index];
      document.querySelectorAll(".zoom-image").forEach((image) => {
        image.style.transform = "none";
      });
    },
    closeModal_img() {
      this.modalImage = null;
    }, //КОНЕЦ
    //Ф-ции при наведении курсора
    zoomIn(event) {
      event.currentTarget.style.transform = "scale(1.1)";
    },
    zoomOut(event) {
      event.currentTarget.style.transform = "scale(1)";
    },

    toggleOption(option) {
      this.selected = option.name;
      this.formData.service = option.value;
      this.areaOpsionsVisible = false;
    }

    async submitForm() {
      try {
        const response = await axios.post('/submition', this.formData);
        console.log("Form successfully submited",response.data);
      } catch (error) {
        console.error("Error occured while submtion form", error);
      }
    }

    SelectOption(option) {
      this.selected = option.name;
      this.areaOpsionsVisible = !this.areaOpsionsVisible;
    },
    //КОНЕЦ
  },
  mounted() {
    document.querySelector(".slider").addEventListener("input", function () {
      let value = this.value;
      document.querySelector("#result-block1").innerText = value * 1200;
      document.querySelector("#result-block2").innerText = value * 300;
    });
  },

  // КОНЕЦ

};
</script>

<template>
  <div class="request">
    <div class="main_request">
      <div class="cl">
        <div class="main_request_correct">
          <h1>Оставить заявку</h1>
          <div class="for_inputs">
            <div class="name_config">
              <p class="your_name">Ваше имя:</p>
              <input
                type="text"
                name="name"
                class="name_contact"
                placeholder="Имя"
                autocomplete="off"
              />
            </div>
            <div class="number_config">
              <p class="numper_phone">Номер телефона:</p>
              <input
                type="text"
                name="name"
                class="name_contact"
                placeholder="Номер"
                autocomplete="off"
              />
            </div>

            <div class="celect_config">
              <p class="celect_service">Выбрать услугу:</p>
              <div class="v_celect">
                <img
                  class="arrow_image"
                  :src="
                    areaOpsionsVisible
                      ? '../src/images/arrow_up.png'
                      : '../src/images/arrow.png'
                  "
                  @click="areaOpsionsVisible = !areaOpsionsVisible"
                />

                <p class="titles">
                  {{ selected }}
                </p>

                <div class="options" v-if="areaOpsionsVisible">
                  <p
                    v-for="option in options"
                    :key="option.value"
                    @click="SelectOption(option)"
                  >
                    {{ option.name }}
                  </p>
                </div>
              </div>
            </div>

            <div class="accept_config" v-if="!areaOpsionsVisible">
              <p class="accept_data_policy">
                Я согласен с политикой обработки моих персональных данных
              </p>
              <input class="input_accept_data_policy" type="checkbox" />
            </div>
          </div>
        </div>
        <button class="button_push_request" v-if="!areaOpsionsVisible">
          Оставить заявку
        </button>
      </div>
      <h1 class="text_price">
        УЗНАТЬ ТОЧНУЮ СТОИМОСТЬ<br />
        И ВСЕ ДЕТАЛИ ПО ДИЗАЙН-ПРОЕКТУ
      </h1>
      <h2 class="more_information">
        Я с вами свяжусь в течении 20-30 минут<br />
        после оставления заявки и отвечу на<br />
        интересующиее вас вопросы
      </h2>
      <div class="create-line"></div>
      <hr />
      <div class="for_background">
        <img
          class="request_background_photo"
          src="../images/photo_laptop_b.png"
        />
      </div>
    </div>
  </div>
</template>

<style></style>
