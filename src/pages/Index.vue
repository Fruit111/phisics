<template>
  <q-page class="flex flex-top row">
    <div class="q-pa-md col">
      <div class="q-gutter-y-md">
        <q-card class="text-bold">
          <q-tabs
            v-model="tab"
            dense
            class="text-bold"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator
          >
            <q-tab class="text-bold" name="mech">
              <div class="text-h6 text-bold">Механика</div>
            </q-tab>
            <q-tab name="therm">
              <div class="text-h6 text-bold">Термодинамика</div>
            </q-tab>
            <q-tab name="optic">
              <div class="text-h6 text-bold">Оптика</div>
            </q-tab>
            <q-tab name="electro">
              <div class="text-h6 text-bold">Электродинамика</div>
            </q-tab>
          </q-tabs>

          <q-separator />

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="mech">
              <div class="text-h4">Механика</div>
              <div class="text-h6">
                это раздел физики, изучающий законы механического движения.
                Основные законы механики открыл великий английский учёный Исаак
                Ньютон , который жил в XVII веке. Механика изучает движение тел
                в различных агрегатных состояниях: твёрдом, жидком и
                газообразном. Механика делится на три раздела: кинематику,
                динамику и статику.
              </div>
              <mechFormulsVue></mechFormulsVue>
            </q-tab-panel>

            <q-tab-panel name="therm">
              <div class="text-h4">Термодинамика</div>
              <div class="text-h6">
                раздел физики, изучающий наиболее общие свойства
                макроскопических систем и способы передачи и превращения энергии
                в таких системах.
              </div>
              <thermoFormuls></thermoFormuls>
            </q-tab-panel>

            <q-tab-panel name="optic">
              <div class="text-h4">Оптика</div>
              <div class="text-h6">
                это раздел физики, изучающий поведение и свойства света, в том
                числе его взаимодействие с веществом и создание инструментов,
                которые его используют или детектируют. Оптика обычно описывает
                поведение видимого, ультрафиолетового и инфракрасного излучения.
              </div>
              <opticFormuls></opticFormuls>
            </q-tab-panel>

            <q-tab-panel name="electro">
              <div class="text-h4">Электродинамика</div>
              <div class="text-h6">
                раздел физики, изучающий электромагнитное поле в наиболее общем
                случае (то есть, рассматриваются переменные поля, зависящие от
                времени) и его взаимодействие с телами, имеющими электрический
                заряд (электромагнитное взаимодействие).
              </div>
              <electroFormuls></electroFormuls>
            </q-tab-panel>
          </q-tab-panels>
        </q-card>
      </div>
    </div>
    <div class="col-12">
      <phisicsCarousel v-if="tab == 'start'"></phisicsCarousel>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import phisicsCarousel from "components/phisicsCarousel.vue";
import mechFormulsVue from "src/components/mechFormuls.vue";
import thermoFormuls from "src/components/thermoFormuls.vue";
import opticFormuls from "src/components/opticFormuls.vue";
import electroFormuls from "src/components/electroFormuls.vue";
import { ref } from "vue";

export default defineComponent({
  name: "PageIndex",
  components: {
    phisicsCarousel,
    mechFormulsVue,
    thermoFormuls,
    opticFormuls,
    electroFormuls,
  },
  setup() {
    return {
      tab: ref("start"),
    };
  },
});
</script>
