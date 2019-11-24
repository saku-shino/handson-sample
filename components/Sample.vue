<template lang="html">
  <div class="">
    <h1>{{ title }}</h1>
    Hello, {{ name }}
    <div>
      {{ reverse }}
    </div>
    <div>
      <button
        @click="plus"
        type="button"
        name="button"
      >
        click times:{{ num }}
      </button>
    </div>
    <div class="slot">
      <slot />
    </div>
    <div :class="[ 'hide', { seven: num === 7}]">
      click 7 times
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Default Title'
    }
  },
  data () {
    return {
      name: 'shino',
      num: 0
    }
  },
  computed: {
    reverse () {
      return this.name.split('').reverse().join('')
    }
  },
  methods: {
    plus () {
      this.num++
    }
  }
}
</script>

<style lang="scss" scoped>
.slot{
  color: red;
}
.hide{
display:none;
&.seven{
  display: block;
  }
}
</style>
