<template>
  <div class="server-tile" @click="() => $router.push(`/server/${serverId}`)">
    <img :src="serverIcon" :alt="serverType">
    <div> {{ serverName }} </div>
    <div class="status" :class="serverOnline" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: ['serverId', 'serverIcon', 'serverName', 'serverType', 'serverOnline'],
  // data() {
  //   return {
  //     serverId: '1',
  //     serverIcon: 'https://clipground.com/images/factorio-logo-8.png',
  //     serverName: 'Factorio game'
  //   }
  // }
});
</script>

<style lang="scss" scoped>
  .server-tile {
    display: flex;
    flex-direction: column;
    width: 100px;
    text-align: center;
    margin: 8px;
    padding: 8px;
    border: 2px gray solid;
    border-radius: 20px;
    cursor: pointer;

    img {
      width: 100px;
    }

    .status {
      width: 16px;
      height: 16px;
      position: absolute;
      border-radius: 50%;

      &.online {
        background-color: green;
      }
      &.starting {
        background-color: yellow;
      }
      &.offline{
        background-color: red;
      }
      &.crashed {
        background-color: black;
      }
    }
  }
</style>