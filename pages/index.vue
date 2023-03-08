<template>
  <div class="server-tiles">
    <ServerTile
      v-for="server in servers"
      :key="server.id"
      :server-id="server.id"
      :server-name="server.name"
      :server-icon="server.icon"
      :server-type="server.type"
      :server-online="server.online"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

type Servers = {
  id: string;
  name: string;
  type: string;
  online: string;
  icon: string;
}[];

export default defineComponent({
  data() {
    return { servers: [] as Servers };
  },
  mounted() {
    $fetch('/api/servers').then(servers => {
      this.servers = servers;
    });
  },
});
</script>

<style lang="scss">
.server-tiles {
  display: flex;  
  justify-content: center;
}
</style>
