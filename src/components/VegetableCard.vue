<template>
  <div
    class="bg-white rounded-3xl shadow-lg overflow-hidden flex flex-col md:flex-row max-w-5xl mx-auto p-2"
  >
    <!-- Image section -->
    <div class="relative rounded-3xl bg-gray-100 w-full md:w-1/2">
      <div class="relative flex justify-center items-center w-full h-full">
        <slot name="image">
          <img
            src=""
            alt="Default image"
            class="w-full h-full object-cover min-h-[300px]"
          />
        </slot>
        <button
          class="absolute top-4 right-4 bg-gray-300 p-2 rounded-full hover:bg-gray-200 transition-colors"
        >
          <CameraIcon class="w-6 h-6" />
        </button>
      </div>
    </div>

    <!-- Content section -->
    <div class="w-full md:w-1/2 p-8">
      <!-- Title section -->
      <div class="mb-8">
        <slot name="title">
          <h2 class="text-2xl font-bold">Default Title</h2>
        </slot>
      </div>

      <!-- Content section -->
      <slot name="content">
        <p class="text-gray-600">No content provided</p>
      </slot>
    </div>
  </div>
</template>

<script setup>
import { CameraIcon } from "lucide-vue-next";
</script>
