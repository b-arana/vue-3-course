<template>
  <Courses />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Courses from "@/components/Courses/index.vue";

export default defineComponent({
  components: {
    Courses,
  },
});
</script>
