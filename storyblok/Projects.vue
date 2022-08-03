<script setup>
defineProps({
  blok: Object,
});
</script>
<template>
  <div class="container project-page">
    <div class="project-title">
      <h1>{{ blok.name || "New Project" }}</h1>
      <NuxtLink :to="{ name: 'index' }">Go Back</NuxtLink>
    </div>

    <div class="project-description">
      <img
        :src="blok.image?.filename || 'https://picsum.photos/300/175'"
        :alt="blok.image?.alt"
      />
      <p>
        {{
          blok.description ||
          "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aut accusantium perferendis molestias, dolorum, ea repellat doloremque, commodi corporis in omnis recusandae facilis laborum ipsum? Alias quos vitae facere aliquam incidunt."
        }}
      </p>
    </div>
  </div>
</template>
