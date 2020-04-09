<template>
  <div class="col-xs-12 col-sm-6" v-if="activeServer">
    <h4>Server #{{ activeServer.id }} Details</h4>
    <p>Status: {{activeServer.status }}</p>
    <button @click="changeStatus">Change Status</button>
  </div>
</template>

<script>
import { eventBus } from "../../main";

export default {
  data() {
    return {
      activeServer: null
    };
  },
  methods: {
    changeStatus() {
      this.activeServer.status = "Normal";
    }
  },
  created() {
    eventBus.$on("serverWasSelected", server => {
      this.activeServer = server;
    });
  }
};
</script>

<style scoped>
div {
  border: 1px solid #ddd;
  border-radius: 4px;
}

h4 {
  border-bottom: 1px solid #ddd;
  padding: 2px 0 10px 0;
}
</style>
