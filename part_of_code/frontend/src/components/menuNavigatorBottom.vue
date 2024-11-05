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
  <div class="bottom">
    <div class="logo_bottom">MALINA<br>PROJECTS.RU</div>
    <div class="navigation_menu_bottom">
      <button @click="forward('.calculate_prices', 150)" class="button_to_prices_bottom">ЦЕНЫ</button>
      <button @click="forward('.about_me', 140)" class="button_to_about_me_bottom">ОБО МНЕ</button>
      <button @click="forward('.service', 80)" class="button_to_services_bottom">УСЛУГИ</button>
      <button @click="forward('.stages', 80)" class="button_to_stages_bottom">ЭТАПЫ</button>
      <button @click="forward('.portfolio', 80)" class="button_to_portfolio_bottom">ПОРТФОЛИО</button>
      <button @click="forward('.request', 30)" class="button_to_request_bottom">ЗАЯВКА</button>
    </div>
    <div class="contacts">
      <p class="information">
        Контакты:<br>
        milkova.alina@mail.ru<br>
        +7-912-271-65-25<br>
        <span class="bullet"></span> Пн-Пт с 8:00-19:00
      </p>
    </div>
  </div>
</template>

<style>

</style>