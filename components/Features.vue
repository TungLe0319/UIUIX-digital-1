<script lang="ts" setup>
const featureItems = [
  {
    title: 'Customization',
    icon: 'gridicons:customize',
    content: `   Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Voluptas nemo corrupti esse, eveniet quos dignissimos,
        accusantium soluta, commodi quae nihil cum tempora omnis.`,
  },
  {
    title: 'Quality Assurance',
    icon: 'iconamoon:certificate-badge-fill',
    content: `   Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Voluptas nemo corrupti esse, eveniet quos dignissimos,
        accusantium soluta, commodi quae nihil cum tempora omnis.`,
  },
  {
    title: 'User Conversion',
    icon: 'material-symbols:person-add-rounded',
    content: `   Lorem ipsum dolor sit amet consectetur adipisicing elit.
        Voluptas nemo corrupti esse, eveniet quos dignissimos,
        accusantium soluta, commodi quae nihil cum tempora omnis.`,
  },
]
</script>

<template>
  <SectionHeaderCenter
    title="What we provide"
    content="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nostrum deserunt, porro quisquam rerum soluta laborum
impedit veniam voluptate culpa iste at quibusdam, facilis fugit expedita?"
    header="Our Services"
  />
  <div class="lg:flex space-y-4 lg:space-y-0  w-full justify-around gap-4 px-4 lg:px-10">
    <div v-for="feature in featureItems" class="  rounded-md lg:w-1/3 bg-[var(--jet)] transition-all duration-150 hover:bg-zinc-800 p-5 space-y-5 flex flex-col items-center justify-center">
      <Icon :name="feature.icon" class=" text-[var(--lavender-blush)]" size="100" />
      <h1 class="font-serif text-xl font-bold lg:text-2xl">
        {{ feature.title }}
      </h1>
      <p class="text-sm lg:text-base">
        {{ feature.content }}
      </p>
      <LeButton variant="outlined" class="  rounded-full text-[var(--bright-pink-crayola)] border-[var(--bright-pink-crayola)] flex items-center justify-center  gap-2">
        <span>Learn More</span>
        <Icon name="mdi:arrow-right-bold-box-outline" size="25" />
      </LeButton>
    </div>
  </div>
</template>

<style></style>
