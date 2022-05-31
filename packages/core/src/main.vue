<script setup lang="ts">
  const props = withDefaults(defineProps<{
    color1?:string,
    color2?:string,
    color3?:string,
    color4?:string,
    color5?:string,
    time?:number,
    angle?:number
  }>(),{
    color1:'#01579B',
    color2:'#00838F',
    color3:'#FFD600',
    color4:'#FF4081',
    color5:'#F44336',
    time:4,
    angle:225
  })

  let times:string = props.time + 's'
  let angle:string = props.angle + 'deg'

</script>

<template>
    <div class="multiColor">
      <slot/>
    </div>
</template>

<style scoped>
.multiColor {
  background:linear-gradient(v-bind('angle'),
    v-bind('props.color1') 0%, v-bind('props.color1') 9%,
    transparent 9%, transparent 10%,
    v-bind('props.color2') 10%, v-bind('props.color2') 19%,
    transparent 19%, transparent 20%,
    v-bind('props.color3') 20%, v-bind('props.color3') 29%,
    transparent 29%, transparent 30%,
    v-bind('props.color4') 30%, v-bind('props.color4') 39%,
    transparent 39%, transparent 40%,
    v-bind('props.color5') 40%, v-bind('props.color5') 49%,
    transparent 49%, transparent 50%,
    v-bind('props.color1')  50%, v-bind('props.color1')  59%,
    transparent 59%, transparent 60%,
    v-bind('props.color2') 60%, v-bind('props.color2') 69%,
    transparent 69%, transparent 70%,
    v-bind('props.color3') 70%, v-bind('props.color3') 79%,
    transparent 79%, transparent 80%,
    v-bind('props.color4') 80%, v-bind('props.color4') 89%,
    transparent 89%, transparent 90%,
    v-bind('props.color5') 90%, v-bind('props.color5') 99%,
    transparent 99%
  );
  background-clip: text;
  -webkit-background-clip: text;
  background-size: 200% 200%;
  color: transparent;
  animation: move v-bind('times') linear infinite;
}
@keyframes move {
  0%{
    background-position: 0px 100%;
  }
  100%{
    background-position: 100% 0px;
  }
}
</style>
