<script setup>
// data for static site gen

const { data: story } = await useAsyncData("story", async ({}) => {
  const story = await useStoryblok("home", {
    version: "draft",
    resolve_relations: "featuredProjects.projects",
  });
  return story.value;
});

// get the live previews working
// onMounted(() => {
//   useStoryblokBridge(
//     story.value.id,
//     (evStory) => {
//       console.log(evStory);
//       story.value = evStory;
//     },
//     {
//       resolveRelations: "featuredProjects.projects",
//     }
//   );
// });
</script>
<template>
  <StoryblokComponent :blok="story.content"></StoryblokComponent>
</template>
