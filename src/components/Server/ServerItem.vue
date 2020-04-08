<template>
  <li class="list-group-item">
    Server #{{ serverId }}
    <span :class="{red: serverStatus != 'Normal'}">{{ serverStatus }}</span>
  </li>
</template>

<script>
export default {
  props: ["serverId", "serverStatus"]
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