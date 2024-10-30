<script setup>
import VegetableCard from "./components/VegetableCard.vue";
import { ref } from "vue";
import {
  StarIcon,
  ClockIcon,
  LeafIcon,
  PlusIcon,
  MinusIcon,
} from "lucide-vue-next";
import PepperIcon from "./assets/img/pepper.png";
import CarrotIcon from "./assets/img/Carrot.png";
import OnionIcon from "./assets/img/Onion.png";
import ZucchiniIcon from "./assets/img/Zucchini.png";
import TomatoIcon from "./assets/img/Tomato.png";

const basketItems = ref([
  {
    name: "Bell Pepper",
    icon: PepperIcon,
    quantity: 3,
    bgColor: "bg-green-100",
  },
  { name: "Carrot", icon: CarrotIcon, quantity: 8, bgColor: "bg-orange-50" },
  { name: "Onion", icon: OnionIcon, quantity: 2, bgColor: "bg-red-50" },
  {
    name: "Zucchini",
    icon: ZucchiniIcon,
    quantity: 1,
    bgColor: "bg-green-100",
  },
  { name: "Tomato", icon: TomatoIcon, quantity: 2, bgColor: "bg-red-100" },
]);
</script>

<template>
  <div class="container flex flex-col gap-5 justify-center">
    <VegetableCard> </VegetableCard>

    <VegetableCard>
      <template #image>
        <img
          class="object-cover min-h-[300px] p-4"
          src="./assets/img/Vegetables basket.png"
        />
      </template>

      <template #title>
        <div class="flex items-center justify-between">
          <h1 class="text-7xl font-medium">Veggy Basket</h1>
          <div class="flex items-center gap-2">
            <span class="text-2xl font-bold">4.7</span>
            <StarIcon class="w-6 h-6 text-yellow-400" />
          </div>
        </div>
      </template>

      <template #content>
        <div class="space-y-8">
          <!-- Basket items -->
          <div>
            <h2 class="text-xl font-semibold mb-4">In your basket</h2>
            <div class="flex flex-wrap gap-4">
              <div
                v-for="(item, index) in basketItems"
                :key="index"
                class="flex flex-col items-center gap-2"
              >
                <div class="rounded-full p-2" :class="item.bgColor">
                  <img :src="item.icon" :alt="item.name" class="w-8 h-8" />
                </div>
                <div class="flex items-center gap-1">
                  <button class="p-1 hover:bg-gray-100 rounded-full">
                    <MinusIcon class="w-4 h-4" />
                  </button>
                  <span
                    class="bg-gray-100 px-4 rounded-xl text-center font-medium"
                    >{{ item.quantity }}</span
                  >
                  <button class="p-1 hover:bg-gray-100 rounded-full">
                    <PlusIcon class="w-4 h-4" />
                  </button>
                </div>
              </div>
            </div>
          </div>

          <!-- Additional info -->
          <div>
            <h2 class="text-xl font-semibold mb-4">Additional Info</h2>
            <div class="flex flex-col sm:flex-row gap-4">
              <div
                class="flex items-center gap-2 bg-slate-100 py-2 px-3 rounded-3xl text-gray-700"
              >
                <ClockIcon class="w-5 h-5" />
                <span
                  >Storage:
                  <strong class="font-medium">10-12 days</strong></span
                >
              </div>
              <div
                class="flex items-center gap-2 bg-slate-100 py-2 px-3 rounded-3xl text-gray-700"
              >
                <LeafIcon class="w-5 h-5" />
                <span
                  >Type:
                  <strong class="font-medium">Mix of vegetables</strong></span
                >
              </div>
            </div>
          </div>
        </div>
      </template>
    </VegetableCard>
  </div>
</template>
