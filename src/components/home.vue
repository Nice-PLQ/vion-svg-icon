
<template>
  <i class="v-icon" @click="click" :style="iconStyle"><svg width="1em" height="1em" viewBox="0 0 48 48" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M25.5555 8.26791L24.2537 7.14508L22.9481 8.26341L20.7826 10.1183L3.86905 24.5845L6.46899 27.6243L9.34513 25.1643V39.0687C9.34513 40.836 10.7778 42.2687 12.5451 42.2687H35.9533C37.7206 42.2687 39.1533 40.836 39.1533 39.0687V25.1788L42.0124 27.6243L44.6123 24.5845L27.9314 10.3173L25.5555 8.26791ZM23.5636 13.0032L23.3817 13.1588L13.3451 21.7557V38.2687H22V30.7824H26V38.2687H35.1533V21.8289L25.3252 13.3517L24.9178 13.0032L24.9192 13.0015L24.2446 12.4197L23.5635 13.0031L23.5636 13.0032Z" fill="currentColor"/>
</svg>
</i>
</template>

<script>
  import { defineComponent, computed } from 'vue';

  const Home = defineComponent({
    name: 'Home',
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

  Home.install = (app) => {
    app.component(Home.name, Home);
  }

  export default Home;
</script>
