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
  <div class="small_section_about_me">
            <img class="interior_photo" src="../images/interior_photo.png" alt="">
            <div class="main_theme">
                <p class="main_text">Дизайн интерьера<br>в Ярославле</p>
                <button @click="forward('.request', 30)" class="button_for_get_consultation">Получить консультацию</button>
            </div>

            <div class="photo_aliny_vitalevny" style="position: relative; display: inline-block;">
                <img src="../images/photo_aliny_vitalevny1.png" alt="">
                <p class="text_on_photo_name">Алина Милкова</p>
                <p class="text_on_photo_profession">Дизайнер интерьера</p>
            </div>
            <!-- <img class="photo_aliny_vitalevny" src="../src/images/photo_aliny_vitalevny.png"> -->
        </div>
</template>