<script setup lang="ts">
const benefits = [
  {
    title: 'Elevate Your Digital Presence',
    content: 'Transform your online presence with innovative and cutting-edge solutions.',
      image: 'https://images.unsplash.com/photo-1521737852567-6949f3f9f2b5?q=80&w=1447&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
  },
  {
    title: 'Craft Seamless Solutions',
    content: 'Create user-friendly and efficient solutions for unmatched online success.',
      image: 'https://images.unsplash.com/photo-1511632765486-a01980e01a18?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
  },
  
  {
    title: 'See the Transformation',
    content: 'Experience boosted engagement and a seamless digital transformation.',
      image: 'https://images.unsplash.com/photo-1523240795612-9a054b0db644?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
  },
  {
    title: 'Boosted Engagement',
    content: 'Enhance user experience and skyrocket conversions for increased success.',
      image: 'https://images.unsplash.com/photo-1520333789090-1afc82db536a?q=80&w=2071&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
  },
];
</script>

<template>
  <main class="p-10 space-y-10 lg:space-y-0">
    <SectionHeader title="Benefits of our Service" header="What we provide" content="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nostrum deserunt, porro quisquam rerum soluta laborum" />
    <section
      v-for="(benefit, index) in benefits" :key="benefit.title" v-motion-fade-visible
      class=" flex flex-col space-y-4 "
    >
      <div class="lg:flex  space-y-4 lg:space-y-0">
        <div :class="index % 2 === 0 ? ' order-1' : ' order-0'" class="flex lg:w-1/2 items-center justify-center">
          <img :src="benefit.image" alt="about image" class="w-full h-full object-cover">
        </div>
        <article :class="index % 2 === 1 ? ' order-1' : ' order-0'" class=" flex lg:w-1/2 flex-col space-y-6 items-center justify-center ">
         
          <h1 class="mb-0 font-serif text-4xl font-bold  ">
            {{ benefit.title }}
          </h1>
        
          <p>
           {{ benefit.content }}
          </p>
        </article>
      </div>
    </section>
  </main>
</template>

<style scoped>

</style>
