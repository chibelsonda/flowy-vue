<template>
  <transition name='scale'>
    <div
      class='indicator'
      :class='{ "not-allowed": !notAllowed }'
      v-show='show'
    />
  </transition>
</template>

<script>
export default {
  name: 'DropIndicator',

  props: {
    show: Boolean,
    notAllowed: Boolean,
  },
};
</script>

<style lang='scss' scoped>
.indicator {
  width: 100%;
  height: 100%;
  border-radius: 4px;
  border: #217ce8 2px solid;
  opacity: 1;
  transition: all 0.3s cubic-bezier(0.05, 0.03, 0.35, 1);
  transform: scale(1);
  position: absolute;
  z-index: 2;
}

.indicator .not-allowed {
  background-color: #f5365c;

  &:after {
    background-color: #f5365c;
  }
}
</style>
