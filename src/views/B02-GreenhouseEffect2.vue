<i18n>
{
  "de": {
    "title": "Was genau ist eigentlich der Treibhauseffekt? 🔆",
    "desc_1": "Ohne Treibhausgase wäre unsere Erdoberfläche sehr kalt (etwa -18 °C).",
    "desc_2": "Je mehr aber dieser Gase in der Atmosphäre sind, umso mehr Wärme wird zurückgehalten und umso mehr erwärmt sich unsere Erde.",
    "desc_3": "Eine Folge: Mehr Wasser aus den Meeren verdunstet und die wärmere Atmosphäre kann mehr Wasserdampf ansammeln. Dadurch erhöht sich beispielsweise das Risiko für extreme Regenfälle.",
    "next_btn": "Weiter"
  },
  "en": {
    "title": "What exactly is the greenhouse effect? 🔆",
    "desc_1": "Without greenhouse gases the earth's surface would be very cold (around -18 °C).",
    "desc_2": "But the more of these gases are in the atmosphere, the more heat is retained and the more our earth warms up.",
    "desc_3": "As a consequence, more water in the oceans evaporates and the warmer atmosphere can accumulate more water vapor. This increases the risk of extreme rainfall, for example.",
    "next_btn": "Continue"
  }
}
</i18n>

<template>
  <div class="modal modal-xl" v-bind:class="{ active: this.$parent.$data.modalOpen }">
    <div class="modal-container">
      <div class="modal-header">
        <a @click="modalClose" class="btn btn-clear float-right" aria-label="Close"></a>

        <div class="modal-title h4">{{ $t("title") }}</div>
      </div>
      <div class="modal-body">
        <div class="columns">
          <div class="column col-7 col-sm-12 mb-3">
            <GreenhouseEffect :animate="true" />
          </div>
          <div class="column col-1 col-sm-2">
            <img
              class="img-responsive"
              v-bind:src="'/assets/wimmel/' + this.$parent.$data.tutor.image"
            />
          </div>
          <div class="column col-4 col-sm-10">
            <p>{{ $t('desc_1') }}</p>
            <p>{{ $t('desc_2') }}</p>
            <p>{{ $t('desc_3') }}</p>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <div class="columns">
          <div class="column col-6 text-left">
            <button @click="navBack" class="btn btn-lg btn">
              <i class="icon icon-arrow-left"></i>
            </button>
          </div>
          <div class="column col-6 text-right">
            <button @click="next" class="btn btn-lg btn-success">
              {{ $t('next_btn') }}
              <i class="icon icon-arrow-right"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GreenhouseEffect from '@/components/GreenhouseEffect.vue';

export default {
  components: {
    GreenhouseEffect,
  },

  methods: {
    next() {
      this.$router.push({ name: 'B03-GreenhouseEffect3' });
    },

    modalClose() {
      this.$parent.modalClose();
    },

    navBack() {
      this.$router.back();
    },
  },
};
</script>
