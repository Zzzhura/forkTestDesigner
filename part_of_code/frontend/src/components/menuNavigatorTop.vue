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
    <div class="navigation_menu_top">
      <div class="logo_top">MALINA<br>PROJECTS.RU</div>
      <div class="list_with_button_to_blocks_top">
        <button @click="forward('.calculate_prices', 150)" class="button_to_prices_top">ЦЕНЫ</button>
        <button @click="forward('.about_me', 140)" class="button_to_about_me_top">ОБО МНЕ</button>
        <button @click="forward('.service', 80)" class="button_to_services_top">УСЛУГИ</button>
        <button @click="forward('.stages', 80)" class="button_to_stages_top">ЭТАПЫ</button>
        <button @click="forward('.portfolio', 80)" class="button_to_portfolio_top">ПОРТФОЛИО</button>
        <button @click="forward('.request', 30)" class="button_to_request_top">ЗАЯВКА</button>
        <button @click="forward('.contacts', 0)" class="button_to_contacts_top">КОНТАКТЫ</button>
      </div>
    </div>
  </template>