<script>
export default {
  name: "ModalButton",
  name_b: "V_celect",
  props: {
    selected: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      images: [
        {url: "..images/project1/project1_1.png"},
        {url: "../images/project1/project1_2.png"},
        {url: "../images/project1/project1_3.png"},
        {url: "../images/project1/project1_4.png"},
        {url: "../images/project1/project1_5.png"},
        {url: "../src/images/project1/project1_6.png"},
        {url: "../images/project1/project1_7.png"},
        {url: "../images/project2/project2_1.png"},
        {url: "../images/project2/project2_2.png"},
        {url: "../images/project2/project2_3.png"},
        {url: "../images/project2/project2_4.png"},
        {url: "../images/project2/project2_5.png"},
        {url: "../images/project2/project2_6.png"},
        {url: "../images/project2/project2_7.png"},
        {url: "../images/project3/project3_1.png"},
        {url: "../images/project3/project3_2.png"},
        {url: "../images/project3/project3_3.png"},
        {url: "../images/project3/project3_4.png"},
        {url: "../images/project3/project3_5.png"},
        {url: "../images/project3/project3_6.png"},
        {url: "../images/project3/project3_7.png"},
        {url: "../images/project3/project3_8.png"},
        {url: "../images/project3/project3_9.png"},
        {url: "../images/project3/project3_10.png"}
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
      pdfUrl: '../assets/our_docs/Мини_дизайн_проект_для_определения_стоимости.pdf',

      selected: 'Услуга',
      areaOpsionsVisible : false,

    };
  },
  methods: {
    showModal(modal) {
      this.modals[modal] = true;
    },
    closeModal(modal) {
      this.modals[modal] = false;
    }
  }
};
</script>


<template>
  <div class="service">
            <nav class="nav_service">
                <p class="title">УСЛУГИ ДИЗАЙНА</p>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>

                <div class="consultion">
                    <span class="nam_of_service">Консультация</span>
                    <span class="description_of_service">Это может быть онлайн или живая встреча</span>
                    <div class="button_wrapper">
                        <span class="price_of_service">1000 руб.</span>
                        <button class="button" @click="showModal('consulation')">Подробнее</button>
                        <div v-if="modals['consultation']" class="modal-shadow" @click.self="closeModal('consultation')">
                            <div class="modal">
                                <div class="modal_container">
                                    <span class="modal_text">Это может быть онлайн или живая встреча.</span>
                                    <span class="modal_text">Стоимость – от 1000 рублей в зависимости
                                    от задачи и времени ее решения.</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>


                <div class="full_design_project">
                    <span class="nam_of_service">Полный<br>дизайн-проект</span>
                    <span class="description_of_service">Предоставление полного дизайн-проекта для интерьера, включая все необходимые планы, спецификации и таблицы для реализации проекта.</span>
                    <div class="button_wrapper">
                        <span class="price_of_service">1200 руб/м<sup>2</sup></span>
                        <button class="button" @click="forward('.stages', 80)">Подробнее</button>
                    </div>
                </div>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>

                <div class="plan_desicion">
                    <span class="nam_of_service">Планировочное<br>решение</span>
                    <span class="description_of_service">Создание полного плана интерьера</span>
                    <div class="button_wrapper">
                        <span class="price_of_service">300 руб/м<sup>2</sup></span>
                        <button class="button" @click="showModal('planDecision')">Подробнее</button>
                        <div v-if="modals['planDecision']" class="modal-shadow" @click.self="closeModal('planDecision')">
                            <div class="modal">
                                <div class="modal_container">
                                    <span class="modal_text">Услуга создания планировочного решения включает:</span>
                                    <span class="modal_text">- Обмерный чертеж с отображением и привязками всех существующих конструкций и коммуникаций;</span>
                                    <span class="modal_text">- План демонтажа существующих перегородок;</span>
                                    <span class="modal_text">- План монтажа новых перегородок;</span>
                                    <span class="modal_text">- План помещения после перепланировки с экспликацией;</span>
                                    <span class="modal_text">- План расстановки мебели;</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>

                <div class="sketchy_project">
                    <span class="nam_of_service">Эскизный проект</span>
                    <span class="description_of_service">Это мини-проект, адаптированный под Вашу задачу.</span>
                    <div class="button_wrapper">
                        <span class="price_of_service">5000 руб/пом.</span>
                        <button class="button" @click="showModal('sketchyProject')">Подробнее</button>
                        <div v-if="modals['sketchyProject']" class="modal-shadow" @click.self="closeModal('sketchyProject')">
                            <div class="modal">
                                <div class="modal_container">
                                    <span class="modal_text">Это мини-проект, адаптированный под Вашу задачу.</span>
                                    <span class="modal_text"><a :href="pdfUrl" target="_blank">Смотреть пример</a></span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>

                <div class="authors_supervision">
                    <span class="nam_of_service">Авторский надзор</span>
                    <span class="description_of_service">Помощь и контроль в процессе реализации дизайн-проекта</span>
                    <div class="button_wrapper">
                        <span class="price_of_service">7000 руб/мес.</span>
                        <button class="button" @click="showModal('authorsProject')">Подробнее</button>
                        <div v-if="modals['authorsProject']" class="modal-shadow" @click.self="closeModal('authorsProject')">
                            <div class="modal">
                                <div class="modal_container">
                                    <span class="modal_text">Данная услуга предполагает:</span>
                                    <span class="modal_text">- регулярный выезд на объект с целью обсуждения с подрядчиком вопросов, возникающих в процессе реализации дизайн-проекта;</span>
                                    <span class="modal_text">- консультирование онлайн и по телефону;</span>
                                    <span class="modal_text">- помощь в подборе отделочных и декоративных материалов, поиск аналогов;</span>
                                    <span class="modal_text">- контроль графика поставок и приемка материалов.</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="line_container">
                    <img src="../images/line.png" class="line">
                </div>
            </nav>
            </div>
</template>