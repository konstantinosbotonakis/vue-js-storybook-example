<template>
  <button class="button-styles" :style="computedStyle" @click="onClick">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'my-disabled-button',
    props: {
      rounded: Boolean
    },
    methods: {
      onClick () {
        this.$emit('click')
      }
    },
    computed: {
      computedStyle () {
        return {
          borderRadius: this.rounded ? '8px' : 0
        }
      }
    }
  }
</script>

<story
  name="Disabled Button"
  methods="{handleClick: action('click')}"
  knobs="{buttonText: text('Button text', 'Disabled Button')}"
  notes="This is a disabled button">
  <my-disabled-button @click="handleClick" :disabled="true">
    {{ buttonText }}
  </my-disabled-button>
</story>

<style>
  .button-styles {
    border: 1px solid #eee;
    background-color: #fff;
    cursor: pointer;
    font-size: 15pt;
    padding: 3px 10px;
    margin: 10px;
  }
</style>
