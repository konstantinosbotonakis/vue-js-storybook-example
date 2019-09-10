<template>
  <button class="button-rounded-styles" :style="computedStyle" @click="onClick">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'my-rounded-button',
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

        }
      }
    }
  }
</script>

<story
  name="Rounded Button"
  methods="{handleClick: action('click')}"
  knobs="{buttonText: text('Button text', 'Rounded')}"
  notes="This is a rounded button">
  <my-rounded-button @click="handleClick" :disabled="false">
    {{ buttonText }}
  </my-rounded-button>
</story>

<style>
  .button-rounded-styles {
    background-color: #fff;
    cursor: pointer;
    font-size: 15pt;
    padding: 3px 10px;
    margin: 10px;
    border-radius: 50%;
    -moz-border-radius: 50%;
  }
</style>
