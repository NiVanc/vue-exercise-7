<template>
  <li class="list-group-item" @click="selectServer">
    Server #{{ server.id }}
    <span :class="{red: server.status != 'Normal'}">{{ server.status }}</span>
  </li>
</template>

<script>
import { eventBus } from "../../main";

export default {
  props: ["server"],
  methods: {
    selectServer() {
      eventBus.selectServer(this.server);
    }
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

li {
  cursor: pointer;
}
</style>