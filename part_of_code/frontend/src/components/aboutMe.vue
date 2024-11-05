<script>
export default {
  methods: {
    forward(className, offset) {
      const element = document.querySelector(className);
      const topPos = element.getBoundingClientRect().top + window.pageYOffset - offset;
      window.scrollTo({ top: topPos, behavior: 'smooth' });
    }
  }
};
</script>

<template>
  <div class="about_me">
            <div class="photo_aliny_vitalevny2" style="position: relative; display: inline;">
                <img src="../images/photo_aliny_vitalevny2.png" alt="" style="position: relative; display: inline;">
            </div>
            <div class="about_me_text">
                Хотите получить уникальный дизайн<br>для своего дома или офиса?
                <div class="light_about_me_text">Я поэтапно расскажу вам о том как всё будет происходить<br>
                от идеи до реализации<br>
                Первая консультация не займет много времени
                </div>
                <button @click="forward('.request', 30)" class="button_for_get_request">Получить консультацию</button>
            </div>
        </div>
</template>