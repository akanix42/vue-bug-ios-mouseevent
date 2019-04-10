<template>
  <div class="hello">
    <h1>{{ count }}</h1>
    <div
      @mouseenter="debugLog.push('mouseenter')"
      @mouseleave="debugLog.push('mouseleave')"
    >
      <button @click="count++">
        Increment button inside mouseenter / mouseleave
      </button>
    </div>
    <div
      @mouseenter="debugLog.push('mouseover')"
      @mouseleave="debugLog.push('mouseout')"
    >
      <button @click="count++">
        Increment button inside mouseover / mouseout
      </button>
    </div>
    <button @click="count++">Increment button standalone</button>
    <ol class="debugLog">
      <li v-for="(message, index) in debugLog" :key="index">{{ message }}</li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      count: 0,
      debugLog: [],
    };
  },
};
</script>

<style scoped lang="scss">
.debugLog {
  position: fixed;
  top: 0;
  right: 0;
  width: 200px;
  height: 200px;
  border: 2px solid red;
}
</style>
