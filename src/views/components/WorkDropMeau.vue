<template>
  <a-dropdown :trigger="['click']">
    <a class="ant-dropdown-link" @click.prevent>
      AI工作台
      <DownOutlined />
    </a>
    <template #overlay>
      <a-menu>
        <a-menu-item key="0">
          <a href="http://www.alipay.com/">AI工作台</a>
        </a-menu-item>
      </a-menu>
    </template>
  </a-dropdown>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import { DownOutlined } from '@ant-design/icons-vue';
export default defineComponent({
  components: {
    DownOutlined,
  },
});
</script>

<style scoped>
  
</style>


