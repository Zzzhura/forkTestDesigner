
<script>
import titleBlock from './components/titleBlock.vue';
import menuNavigatorTop from './components/menuNavigatorTop.vue';
import pricesBlock from './components/pricesBlock.vue';
import aboutMe from './components/aboutMe.vue';
import myAdvantages from './components/myAdvantages.vue';
import services from './components/services.vue';
import steps from './components/steps.vue';
import portfolio from './components/portfolio.vue';
import forma from './components/forma.vue';
import menuNavigatorBottom from './components/menuNavigatorBottom.vue';
export default {
  components:
      {
        menuNavigatorTop,
        titleBlock,
        pricesBlock,
        aboutMe,
        myAdvantages,
        services,
        steps,
        portfolio,
        forma,
        menuNavigatorBottom
      },
  }

</script>
<template>
  <menuNavigatorTop />
  <titleBlock />
  <pricesBlock />
  <aboutMe />
  <myAdvantages />
  <services />
  <steps />
  <portfolio/>
  <forma />
  <menuNavigatorBottom />
</template>

<style>
</style>
