
<template>
  <i class="v-icon" @click="click" :style="iconStyle"><svg width="1em" height="1em" viewBox="0 0 48 48" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M5 9C5 6.79086 6.79086 5 9 5H17V9H9V17H5V9ZM38 22H10V26H38V22ZM5 39C5 41.2091 6.79086 43 9 43H17V39H9V31H5V39ZM43 9C43 6.79086 41.2091 5 39 5H31V9H39V17H43V9ZM43 39C43 41.2091 41.2091 43 39 43H31V39H39V31H43V39Z" fill="currentColor"/>
</svg>
</i>
</template>

<script>
  import { defineComponent, computed } from 'vue';

  const Scan = defineComponent({
    name: 'Scan',
    props: {
      color: String,
      size: String,
    },
    emits: ['click'],
    setup(props, ctx) {
      const iconStyle = computed(() => ({
        display: 'inline-block',
        fontSize: props.size,
        color: props.color,
        width: '1em',
        height: '1em',
        lineHeight: '1em',
      }));

      const click = (e) => ctx.emit('click', e);

      return { iconStyle, click };
    }
  });

  Scan.install = (app) => {
    app.component(Scan.name, Scan);
  }

  export default Scan;
</script>
