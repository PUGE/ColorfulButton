<template>
  <div class="button" @mousemove="move" @click.stop="$emit('onClick')" v-once>
    <span>{{text}}</span>
  </div>
</template>

<script>
  export default {
    props: {
      text: String
    },
    methods: {
      move (e) {
        const x = e.pageX - e.target.offsetLeft
        const y = e.pageY - e.target.offsetTop
        e.target.style.setProperty('--x', `${ x }px`)
        e.target.style.setProperty('--y', `${ y }px`)
      }
    }
  }
</script>

<style lang='less'>
  .button {
    position: relative;
    background: #f72359;
    padding: 1em 2em;
    border: none;
    color: white;
    font-size: 1.2em;
    cursor: pointer;
    outline: none;
    overflow: hidden;
    border-radius: 100px;
  }
  .button:before {
    --size: 0;  
    content: '';
    position: absolute;
    left: var(--x);
    top: var(--y);
    width: var(--size);
    height: var(--size);
    background: radial-gradient(circle closest-side, #4405f7, transparent);
    transform: translate(-50%, -50%);
    transition: width .2s ease, height .2s ease;
  }
  .button:hover::before {
    --size: 400px;
  }
  .button span {
    position: relative;
  }
</style>
