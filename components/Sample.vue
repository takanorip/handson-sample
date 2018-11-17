<template lang="html">
  <div class="">
    <h1>{{ title }}</h1>
    Hello, {{ name }}
    <div>
      {{ reverse }}
    </div>
    <div>
      <button
        type="button"
        name="button"
        @click="plus">
        {{ num }}
      </button>
    </div>
    <div class="slot">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default title'
    }
  },
  data() {
    return {
      name: 'takanori oki',
      num: 0
    }
  },
  computed: {
    reverse() {
      return this.name
        .split('')
        .reverse()
        .join('')
    }
  },
  methods: {
    plus() {
      this.num++
    }
  }
}
</script>

<style lang="css">
.slot {
  color: red;
}
</style>
