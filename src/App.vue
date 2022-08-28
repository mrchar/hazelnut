<template>
  <div class="screen-wrapper">
    <Theme>
      <div class="view-wrapper h-full p-8 flex justify-center items-center">
        <button class="w-16 p-2 text-center bg-white rounded shadow" @click.self="showModal=true">
          显示
        </button>
        <Modal v-model="showModal">
          <div>
            Hello World
          </div>
        </Modal>
      </div>
    </Theme>

  </div>
</template>

<script setup>
import {ref} from "vue"
import Theme from "@/components/basic/Theme.vue"
import Modal from "@/components/basic/Modal.vue"

const showModal = ref(true)
</script>

<style>
.screen-wrapper {
  @apply w-screen h-screen;
}

.view-wrapper {
  @apply container mx-auto;
}
</style>