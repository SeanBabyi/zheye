<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
    <a href="#" class="navbar-brand">者也专栏</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">登录</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">注册</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <DropdownVue :title="`你好 ${user?.name}`">
          <DropdownItemVue
            ><a href="#" class="dropdown-item">新建文章</a></DropdownItemVue
          >
          <DropdownItemVue disabled
            ><a href="#" class="dropdown-item">编辑资料</a></DropdownItemVue
          >
          <DropdownItemVue
            ><a href="#" class="dropdown-item">退出登录</a></DropdownItemVue
          >
        </DropdownVue>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import DropdownVue from "@/components/Dropdown.vue";
import DropdownItemVue from "@/components/DropdownItem.vue";
export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
defineProps<{ user: UserProps }>();
</script>
