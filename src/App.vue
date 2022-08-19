<template>
  <div class="screen-wrapper">
    <Theme backgroundImage="https://source.unsplash.com/random">
      <div class="view-wrapper">
        <div class="max-w-2xl p-10 mx-auto flex flex-col gap-2">
          <div v-for="(todo, index) in todos" :key="index">
            <Card>
              <CheckBox></CheckBox>
              <span class="mx-2"> {{ todo.summary }}</span>
            </Card>
          </div>
          <div>
            <Card>
              <form action="">
                <input type="textarea" value="第三件事">
              </form>
              <div class="text-right">
                <Button>添加</Button>
              </div>
            </Card>
          </div>
        </div>
      </div>
    </Theme>
  </div>
</template>

<script setup>
import { ref } from "vue"
import Theme from "@/components/Theme.vue"
import CheckBox from "@/components/CheckBox.vue"
import Card from "@/components/Card.vue"
import Button from "@/components/Button.vue"
const todos = ref([
  {
    summary: "第一件事",
    description: "描述可以不写",
    status: "ready"
  },
  {
    summary: "第二件事",
    description: "描述可以不写",
    status: "ready"
  }
])
</script>

<style>
.screen-wrapper {
  @apply w-screen h-screen;
}

.view-wrapper {
  @apply container mx-auto;
}
</style>