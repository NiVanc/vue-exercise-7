<template>
  <li class="list-group-item" @click="showServerDetails">
    Server #{{ server.id }}
    <span :class="{red: server.status != 'Normal'}">{{ server.status }}</span>
  </li>
</template>

<script>
export default {
  props: ["server"],
  methods: {
    showServerDetails() {}
  }
};
</script>

<style scoped>
span {
  text-align: right;
  color: green;
  float: right;
}

.red {
  color: red;
}
</style>