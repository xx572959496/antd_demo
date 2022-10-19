<template>
  <a-layout style="min-height: 100vh">
    <a-layout-sider theme="light">
      <div class="logo" />
      <a-menu>
        <a-menu-item>菜单项</a-menu-item>
        <a-sub-menu key="sub1" title="子菜单">
          <template #icon>
            <MailOutlined />
          </template>
          <a-menu-item>子菜单项</a-menu-item>
        </a-sub-menu>
      </a-menu>
    </a-layout-sider>
  </a-layout>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    msg: String
  }
}
</script>

<style scoped>
.logo {
  height: 32px;
  margin: 16px;
  background: rgba(255, 255, 255, 0.3);
}
</style>