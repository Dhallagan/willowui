<template>
  <div class="row">
      <template v-if="sectioned" v-for="slot, name in $slots">
          <willow-layout-section>
              <slot :name="name"></slot>
          </willow-layout-section>
      </template>
      <template v-if="!sectioned" v-for="slot, name in $slots">
          <slot :name="name"></slot>
      </template>
  </div>
</template>

<script>
export default {
  name: "willow-page",

  props: {
    sectioned: {
      type: Boolean,
      default: false
    }
  }
};
</script>
