<template>
  <q-layout view="hHh Lpr lFf" class="bg-primary text-white">
    <q-header elevated class="bg-secondary q-pa-sm" height-hint="98">
      <q-toolbar class="row">
        <!-- <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" /> -->
        <div class="col-1"></div>
        <q-toolbar-title class="col-shrink">
          <q-avatar>
            <q-icon name="refresh" size="sm" />
          </q-avatar>
          Email Client
        </q-toolbar-title>
        <q-tabs class="col q-mx-lg" align="justify">
          <q-route-tab to="/page1" label="Page One" class="tab" />
          <q-route-tab to="/page2" label="Page Two" class="tab" />
          <q-route-tab to="/page3" label="Page Three" class="tab" />
        </q-tabs>
        <q-input
          dark
          filled
          color="accent"
          label-color="white"
          bg-color="grey-9"
          class="col-3 text-white text-body2 q-mr-md"
          v-model="searchText"
          label="Search"
          clearable
          clear-icon="close"
          icon-color="accent"
          type="search"
        >
          <template v-slot:prepend>
            <q-icon name="search" color="accent"></q-icon>
          </template>
        </q-input>
      </q-toolbar>
    </q-header>

    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      :mini="miniState"
      @mouseover="miniState = false"
      @mouseout="miniState = true"
      :width="200"
      :breakpoint="500"
      :mini-width="75"
      class="bg-secondary"
      padding
      elevated
    >
      <q-list padding>
        <!-- <q-item-label header class="text-white">Testings</q-item-label>
          <q-separator></q-separator> -->
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon
              name="inbox"
              draggable="false"
              color="accent"
              size="md"
            ></q-icon>
          </q-item-section>
          <q-item-section class="text-body2"> Inbox </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <q-list padding class="">
        <q-infinite-scroll @load="onLoad" :offset="500">
          <email-component
            v-for="email in emails"
            :key="email.id"
            :sender="email.sender"
            :description="email.description"
          ></email-component>
          <template v-slot:loading>
            <div class="row justify-center q-my-md">
              <q-spinner-dots color="accent" size="lg" />
            </div>
          </template>
        </q-infinite-scroll>
      </q-list>
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import EmailComponent from 'src/components/EmailComponent.vue';
import { ref } from 'vue';

const leftDrawerOpen = ref(true);
const miniState = ref(true);
const searchText = ref('');

let id = 0;

const emails = ref([
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
  {
    id: id++,
    sender: 'Test',
    subject: 'Subject',
    description:
      'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
  },
]);

// function toggleLeftDrawer() {
//   leftDrawerOpen.value = !leftDrawerOpen.value;
// }
// eslint-disable-next-line @typescript-eslint/no-explicit-any
function onLoad(index: number, done: () => void) {
  setTimeout(() => {
    emails.value.push(
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      },
      {
        id: id++,
        sender: 'Test',
        subject: 'Subject',
        description:
          'eteutrhtkerkeraaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaahykoehrykerokyhkerhtyokhertkhert',
      }
    );
    done();
  }, 1000);
}
</script>

<style lang="scss" scoped>
.tab {
  border-radius: 1.1em;
}
</style>
