<template>
  <p class="error">
    若長時間出現此訊息，請確保你已經啟用Javascript！<br>又或者線上監控主服務（伺服器端）尚未啟動或已關閉。
  </p>
</template>
<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'TheError'
});
</script>
<style>
p.error {
  text-align: center;
  color: #616366;
  margin-bottom: 0;
}
</style>
