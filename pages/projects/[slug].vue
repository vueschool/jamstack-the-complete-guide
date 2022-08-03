<script setup>
const route = useRoute();
const story = await useStoryblok(`projects/${route.params.slug}`, {
  version: "draft",
});
</script>
<template>
  <StoryblokComponent v-if="story" :blok="story.content"></StoryblokComponent>
</template>
