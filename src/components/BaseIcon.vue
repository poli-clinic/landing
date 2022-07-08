<template>
  <img :src="iconComponent" width="64"/>
</template>

<script>
import green from '../assets/icons/icon-socks-green.svg';
import azure from '../assets/icons/icon-socks-azure.svg';
import red from '../assets/icons/icon-socks-red.svg';

const icons = {
  green_socks: green,
  azure_socks: azure,
  red_socks: red,
}

export default {
  props: {
    name: {
      type: String,
      required: true,
      validator(value) {
        return Object.prototype.hasOwnProperty.call(icons, value)
      }
    }
  },

  computed: {
    iconComponent() {
      return icons[this.name]
    }
  }
}
</script>
