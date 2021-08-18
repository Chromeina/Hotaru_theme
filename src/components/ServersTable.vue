<template>
  <table class="ui basic unstackable table" id="table">
    <thead>
    <tr>
      <th id="status4">運作狀態</th>
      <th id="name">節點名稱</th>
      <th id="type">類型</th>
      <th id="location">伺服器位置</th>
      <th id="uptime">在線時間</th>
      <th id="load">負載</th>
      <th id="network">網路(B/s) ↓|↑</th>
      <th id="traffic">流量(B) ↓|↑</th>
      <th id="cpu">CPU</th>
      <th id="ram">記憶體</th>
      <th id="hdd">硬碟</th>
    </tr>
    </thead>
    <tbody id="servers">
    <!-- Servers here \o/ -->
    <!--
    use index for the key may cause performance issues when delete a server from array,
    but not a big matter and we cannot find a more suitable data for the unique key.
    -->
    <table-item v-for="(server, index) of servers" :key="index" :server="server"/>
    </tbody>
  </table>
</template>
<script lang="ts">
import { defineComponent, PropType } from 'vue';
import TableItem from '@/components/TableItem.vue';

export default defineComponent({
  name: 'ServersTable',
  props: {
    servers: {
      type: Array as PropType<Array<StatusItem | BoxItem>>,
      default: () => ([])
    }
  },
  components: {
    TableItem
  }
});
</script>
<style>
#table {
  font-size: 1rem;
  border: none;
  text-align: center;
  vertical-align: middle;
}

#table thead tr th {
  color: #9da2a6;
  white-space: nowrap;
}
</style>
