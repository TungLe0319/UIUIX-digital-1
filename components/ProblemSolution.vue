<script lang="ts" setup>

</script>

<template>
  <div class="flex w-full flex-col items-center justify-center  p-10 lg:flex-row ">
    <div class="flex w-full items-center justify-center lg:w-1/2 mb-10 lg:mb-0">
      <iframe
        class="rounded-md shadow-2xl" width="560" height="315"
        src="https://www.youtube.com/embed/NpEaa2P7qZI?si=AYGfNW0zFeyJNnVg" title="YouTube video player" frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      />
    </div>
    <div class="flex flex-col items-center justify-center lg:w-1/2 lg:pl-10">
      <SectionHeader
        header="Problem/Solution" title="Find the right solution for your business"
        content="Lorem ipsum, dolor sit amet consectetur adipisicing elit. Repudiandae modi doloremque, deserunt optio harum,
            officia veniam voluptatibus expedita architecto quibusdam perspiciatis nam rem. Ratione delectus aut a modi
            suscipit accusamus atque assumenda aliquid ipsum aperiam, earum praesentium quod dolores sapiente quo
            explicabo vero commodi. Odio repudiandae neque nobis animi nihil!"
      />
      <div class="mt-3 space-y-3">
        <div class="flex">
          <div class="mx-3 h-fit">
            <Icon name="fluent:person-support-16-filled" color="" size="50" />
          </div>
          <div class="lg:w-3/4">
            <div>
              <h1 class="font-serif text-xl font-bold lg:text-2xl">
                Quick Support
              </h1>
              <p class="text-sm lg:text-base">
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Voluptas nemo corrupti esse, eveniet quos dignissimos,
                accusantium soluta, commodi quae nihil cum tempora omnis.
              </p>
            </div>
          </div>
        </div>
        <div class="flex">
          <div class="mx-3 h-fit">
            <Icon name="ph:certificate-duotone" color="" size="50" />
          </div>
          <div class="lg:w-3/4">
            <div>
              <h1 class="font-serif text-xl font-bold lg:text-2xl">
                Proven Quality
              </h1>
              <p class="text-sm lg:text-base">
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
                Voluptas nemo corrupti esse, eveniet quos dignissimos,
                accusantium soluta, commodi quae nihil cum tempora omnis.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
