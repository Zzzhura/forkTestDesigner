<script>
export default {
  methods: {
    forward(className, offset) {
      const element = document.querySelector(className);
      const topPos = element.getBoundingClientRect().top + window.pageYOffset - offset;
      window.scrollTo({ top: topPos, behavior: 'smooth' });
    }
  },
  mounted() {
    document.querySelector('.slider').addEventListener('input', function() {
      let value = this.value;
      document.querySelector('#result-block1').innerText = value * 1200;
      document.querySelector('#result-block2').innerText = value * 300;
    });
  },
};

</script>

<template>
  <div class="calculate_prices">
            <p class="title_price">РАСЧЕТ ЦЕНЫ</p>
                <div class="counting_block">
                    <div class="slider_block">
                        <p class="calc_text">
                            Площадь помещения <span id="rangeValue"> 80</span> м²
                        </p> 
                        <input class="slider" type="range" min="15" max="300" value="80" oninput="rangeValue.innerText = this.value">
                    </div>
                    
                    <div class="output1">
                        <p class="text_inside_output">Полный дизайн-проект</p>
                        <p class="total_price">
                            От <span id="result-block1">96000</span> рублей
                            <button @click="forward('.service', 80)" class="button_for_get_more">Подробнее</button>
                        </p>
                    </div>
                    <div class="output2">
                        <p class="text_inside_output">Планировочное решение</p>
                        <p class="total_price">
                            От <span id="result-block2">24000</span> рублей
                            <button @click="forward('.service', 80)" class="button_for_get_more">Подробнее</button>
                        </p>
                    </div>
                </div>
        </div>
</template>
