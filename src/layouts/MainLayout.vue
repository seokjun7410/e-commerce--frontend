<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-primary">
      <q-toolbar>
        <q-btn
          class="bg-dark"
          flat
          dense
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title class="text-dark"> HODING</q-toolbar-title>

        <div class="text-dark">로그인</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-item-label header>계정 정보</q-item-label>
      <q-item class="q-mb-sm" clickable v-ripple>
        <q-item-section avatar>
          <q-avatar>
            <img
              :src="`https://image-proxy.sta1.com/_up/shop/logo/2019/06/1559710017170_mi.jpg`"
            />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label> 홍석준 </q-item-label>
          <q-item-label caption lines="1"> thgks779@naver.com </q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-icon name="settings" color="grey" />
        </q-item-section>
      </q-item>

      <q-item clickable v-ripple>
        <q-item-section>
          <q-item-label>장바구니</q-item-label>
        </q-item-section>
      </q-item>

      <q-item clickable v-ripple>
        <q-item-section>
          <q-item-label>즐겨찾기</q-item-label>
        </q-item-section>
      </q-item>

      <q-separator spaced />

      <q-list>
        <q-item-label header> CATEGORY </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<script>
const linksList = [
  {
    title: '할인 상품',
    caption: 'ON SALE',
    link: 'https://github.com/quasarframework',
    color: 'text-red',
  },
  {
    title: '인기 상품',
    caption: 'BEST',
    link: 'https://github.com/quasarframework',
    color: 'text-red',
  },

  {
    title: '상의',
    caption: 'TOP',
    link: 'https://chat.quasar.dev',
  },
  {
    title: '하의',
    caption: 'BOTTOM',
    link: 'https://forum.quasar.dev',
  },
  {
    title: '아우터',
    caption: 'OUTER',
    link: 'https://twitter.quasar.dev',
  },
];
</script>
<script setup>
import { ref } from 'vue';
import EssentialLink from 'components/EssentialLink.vue';

const leftDrawerOpen = ref(false);
const essentialLinks = linksList;
const toggleLeftDrawer = () => (leftDrawerOpen.value = !leftDrawerOpen.value);
</script>
